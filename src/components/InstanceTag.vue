<template>
    <h2 class="subtitle">实例标识</h2>
    <div class="columns is-desktop is-variable is-1">
        <div class="column">
            <input v-model="region" class="input" type="text" placeholder="地域（城市 / 地区）">
        </div>
        <div class="column">
            <input v-model="isp" class="input" type="text" placeholder="主机商 / 互联网提供商">
        </div>
        <div class="column">
            <input v-model="maintainer" class="input" type="text" placeholder="维护 / 捐赠者昵称（可选）">
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
            region: '',
            isp: '',
            maintainer: '',
        }
    },
    computed: {
        utag() {
            return `${this.region}-${this.isp}${this.maintainer ? '-' + this.maintainer : ''}-${this.uid}`
        },
        uid() {
            let _ = this.region + this.isp + this.maintainer // 三个值中的任何一个发生变化都会更新 uid
            return uuidv4().toString().substring(0, 8)
        }
    }
}
</script>