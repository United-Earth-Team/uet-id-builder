<template>
    <h2 class="subtitle">服务标识</h2>
    <div class="columns is-desktop is-variable is-1">
        <div class="column">
            <input v-model="service" class="input" type="text" placeholder="服务名称">
        </div>
        <div class="column">
            <input v-model="zone" class="input" type="text" placeholder="区域 ID（可选）">
        </div>
    </div>
    <div>
        <div class="control">
            <input class="input is-primary" type="text" :value="utag" readonly>
        </div>
    </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid'

export default {
    data() {
        return {
            service: '',
            zone: '',
        }
    },
    computed: {
        utag() {
            return `${this.service}-${this.uid}${this.zone ? '.srv-zone-' + this.zone : ''}`
        },
        uid() {
            let _ = this.service + this.zone // 两个值中的任何一个发生变化都会更新 uid
            return uuidv4().toString().substring(0, 8)
        }
    }
}
</script>