<template>
    <h2 class="subtitle">快速识别图</h2>
    <div>
        <div class="control">
            <input class="input" type="text" placeholder="标识 / 字符串" v-model="utag">
        </div>
    </div>
    <div class="mt-5">
        <article class="media">
            <figure class="media-left">
                <p v-if="avatarCode" class="image is-128x128">
                    <img :src="avatarCode">
                </p>
                <article v-else class="message" style="height: 128px;">
                    <div class="message-header">
                        <p>提示</p>
                    </div>
                    <div class="message-body has-text-centered">
                        图片将会生成在此处
                        <br>
                        复制右侧的 URI 即可在别处使用
                    </div>
                </article>
            </figure>
            <div class="media-content">
                <textarea class="textarea has-fixed-size is-small is-primary" placeholder="图片的 DataURI 将会生成在此处"
                    style="height: 128px;" :value="avatarCode" readonly></textarea>
            </div>
        </article>
    </div>
</template>

<script>
import { generateFromString } from 'generate-avatar'

export default {
    data() {
        return {
            utag: ''
        }
    },
    computed: {
        avatarCode() {
            return this.utag ? 'data:image/svg+xml;base64,' + btoa(generateFromString(this.utag)) : ''
        }
    }
}
</script>