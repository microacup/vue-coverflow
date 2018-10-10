<template>
    <div v-coverflow class="coverflow">
        <div v-for="(coverItem, index) of coverList" :key="index" class="cover-card">
            <div :style="customStyle(index)" class="cover-card-head">
                <img :src="coverItem.cover" class="cover-avatar">
                <!-- <div :src="coverItem.cover" class="cover-rank">
                    NO.1
                </div> -->
                <div class="cover-title">{{ coverItem.title }}</div>
            </div>
            <div class="cover-card-body">
                {{ coverItem.content }}
            </div>
            <div class="cover-card-footer">
                <div class="up-down">
                    <!-- <Icon type="ios-thumbs-up"></Icon> -->
                    <span>10</span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import coverflow from './directives/coverflow';

export default {
    name: 'Coverflow',

    data() {
        return {
            coverIndex: 0,
            colors: [
                'pink',
                'blue',
                'green',
                'red',
                'coral',
            ],
        };
    },
    props: {
        coverList: {
            type: Array,
            required: true,
        },
        width: {
            type: Number,
            default: 980,
        },
        bgColor: {
            type: String,
            default: 'transparent',
        },
        index: {
            type: Number,
            default: 0,
        },
        coverWidth: {
            type: Number,
            default: 100,
        },
        coverHeight: {
            type: Number,
            default: 0,
        },
        coverSpace: {
            type: Number,
            default: 50,
        },
        coverShadow: {
            type: Boolean,
            default: false,
        },
        coverFlat: {
            type: Boolean,
            default: false,
        },
    },
    methods: {
        handleChange(index) {
            this.coverIndex = index;
            this.$emit('change', index);
        },
        customStyle(index) {
            const colorIndex = index % this.colors.length;
            return `background: ${this.colors[colorIndex]};`;
        },
    },
    directives: {
        coverflow,
    },
};
</script>
<style>
.cover-card {
    background: white;
    height: 300px;
    width: 240px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    text-align: center;
    font-size: 16px;
    cursor: pointer;
    border-radius: 10px;
    box-shadow: -2px 15px 11px 7px #1e2a3a30;
}
.cover-card-head {
    height: 90px;
    width: 100%;
    position: relative;
    border-radius: 10px 10px 0 0;
    color: white;
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center;
}
.cover-avatar {
    width: 80px;
    height: 80px;
    border-radius: 50%;
    background: white;
    padding: 5px;
    position: relative;
    top: -40px;
}
.cover-rank {
    position: relative;
    top: -55px;
    background-size: contain;
    background-repeat: no-repeat;
    background-position: center;
    background-color: whitesmoke;
    height: 24px;
    line-height: 18px;
    font-size: 12px;
    font-weight: bold;
    font-style: italic;
}
.cover-title {
    position: relative;
    top: -30px;
    font-size: 16px;
}
.cover-card-body {
    padding: 10px 20px;
    width: 100%;
    line-height: 1.5em;
    text-align: justify;
    overflow-y: auto;
}

.cover-card-footer {
    height: 50px;
    line-height: 50px;
    width: 100%;
}
</style>
