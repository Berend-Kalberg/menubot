<template>
    <div class="rich-card" tabindex="0">
        <img v-if="imageUri" class="rich-card-image" :src="imageUri" :alt="imageTitle || title">
        <div class="rich-card-content">
            <div v-if="title" class="rich-card-title">{{title}}</div>
            <div v-if="subtitle" class="rich-card-subtitle">{{subtitle}}</div>
            <div v-if="text" class="rich-card-text">{{text}}</div>
            <slot />
        </div>
    </div>
</template>

<style lang="sass" scoped>
.rich-card
    background-color: var(--component-background)
    box-shadow: var(--shadow)
    border-radius: 12px

.rich-card-image
    width: 100%
    height: auto
    object-fit: cover
    border-top-right-radius: 10px
    border-top-left-radius: 10px
    background-color: var(--image-background)

.rich-card-content
    padding: 16px

.rich-card-title
    font-weight: 500
    font-size: 20px
    color: var(--text)
    line-height: 24px
    overflow: hidden
    text-overflow: ellipsis

.rich-card-subtitle
    font-size: 16px
    line-height: 24px
    color: var(--text-subtitle)

.rich-card-text
    line-height: 24px
    font-size: 14px
    color: var(--text-secondary)
    white-space: normal
</style>

<script>
export default {
    name: 'RichCard',
    props: {
        text: {
            type: String,
            default: null
        },
        imageUri: {
            type: String,
            default: null
        },
        imageTitle: {
            type: String,
            default: null
        },
        subtitle: {
            type: String,
            default: null
        },
        title: {
            type: String,
            default: null
        }
    }
}
</script>
