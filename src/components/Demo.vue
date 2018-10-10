<template>
  <div class="demo">
    <h2>Demo 1</h2>
    <coverflow :cover-list="coverList" :cover-height="300" :cover-width="240" :cover-space="40"
      :index="2" bg-color="#1e2a3a" @change="handleChange"></coverflow>
    <pre v-highlightjs>
      <code class="javascript">
        // all example uses the same js
        import { coverflow } from 'vue-coverflow'

        export default {
          name: 'app',
          data () {
            return {
              coverList: [
                {
                    cover: require('../assets/images/react.png'),
                    title: 'React',
                    content: `一个常见的设置是使用其它数据库作为主要的数据存`,
                },
                {
                    cover: require('../assets/images/angular.png'),
                    title: 'Angular',
                    content: `一个常见的设置是使用其它数据库作为主要的数据存储，`,
                },
                {
                    cover: require('../assets/images/vue.png'),
                    title: 'Vue',
                    content:
                        '使用 Elasticsearch 做数据检索，这意味着主数据库的所有更改发生时都需要被复制到 Elasticsearch',
                },
                {
                    cover: require('../assets/images/webpack.png'),
                    title: 'Webpack',
                    content: '如果你的主数据库已经有了版本号 — 或一个能作为版本号的字段值比如',
                },
                {
                    cover: require('../assets/images/yarn.png'),
                    title: 'Yarn',
                    content: '如果你的主数据库已经有了版本号 — 或一个能作为版本号的字段值比如',
                },
            ]
            }
          },
          components: {
            coverflow
          }
        }
      </code>
      <code class="html">{{ codeOne }}</code>
    </pre>
    <h2>Demo 2</h2>
    <coverflow :coverList="coverList" :cover-height="300" :coverWidth="260" :index="2" bgColor="#333"></coverflow>
    <pre v-highlightjs>
      <code class="html">{{ codeTwo }}</code>
    </pre>
    <h2>Demo 3</h2>
    <coverflow :coverList="coverList" :cover-height="300" :coverWidth="260" :index="2" :coverShadow="true"
      bgColor="#92acc1"></coverflow>
    <pre v-highlightjs>
      <code class="html">{{ codeThree }}</code>
    </pre>
    <h2>Demo 4</h2>
    <coverflow :coverList="coverList" :cover-height="300" :coverWidth="260" :coverSpace="100"
      :index="0" :coverFlat="true"></coverflow>
    <pre v-highlightjs>
      <code class="html">{{ codeFour }}</code>
    </pre>
  </div>
</template>

<script>
export default {
    name: 'Demo',
    data() {
        return {
            coverList: [
                {
                    cover: require('../assets/images/react.png'),
                    title: 'React',
                    content: `一个常见的设置是使用其它数据库作为主要的数据存储，使用 Elasticsearch 做数据检索，
           这意味着主数据库的所有更改发生时都需要被复制到 Elasticsearch ，如果多个进程负责这一数据同步，
           你可能遇到类似于之前描述的并发问题。如果你的主数据库已经有了版本号 — 或一个能作为版本号的字段值比如 timestamp — 
           那么你就可以在 Elasticsearch 中通过增加 version_type=external 
          到查询字符串的方式重用这些相同的版本号， 版本号必须是大于零的整数， 且小于 9.2E+18 — 一个 Java 中 long 类型的正值。`,
                },
                {
                    cover: require('../assets/images/angular.png'),
                    title: 'Angular',
                    content: `一个常见的设置是使用其它数据库作为主要的数据存储，`,
                },
                {
                    cover: require('../assets/images/vue.png'),
                    title: 'Vue',
                    content:
                        '使用 Elasticsearch 做数据检索，这意味着主数据库的所有更改发生时都需要被复制到 Elasticsearch',
                },
                {
                    cover: require('../assets/images/webpack.png'),
                    title: 'Webpack',
                    content: '如果你的主数据库已经有了版本号 — 或一个能作为版本号的字段值比如',
                },
                {
                    cover: require('../assets/images/yarn.png'),
                    title: 'Yarn',
                    content: '如果你的主数据库已经有了版本号 — 或一个能作为版本号的字段值比如',
                },
            ],
            codeOne: `
      <coverflow :coverList="coverList" :coverWidth="260" :index="2"></coverflow>
      `,
            codeTwo: `
      <coverflow :coverList="coverList" :coverWidth="260" :index="2" bgColor="#ddd"></coverflow>
      `,
            codeThree: `
      <coverflow :coverList="coverList" :coverWidth="260" :index="2" :coverShadow="true"></coverflow>
      `,
            codeFour: `
      <coverflow :coverList="coverList" :coverWidth="260" :coverSpace="100" :index="0" :coverFlat="true"></coverflow>
      `,
        };
    },
    methods: {
        handleChange(index) {
            // eslint-disable-next-line
            console.log(`[Demo 1] You have click cover ${index}`);
        },
    },
};
</script>

<style scoped>
.demo {
    width: 980px;
    margin: 0 auto;
}
</style>
