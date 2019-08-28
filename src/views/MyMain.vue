<template>
<main>
  <my-section v-for="(secs, index) in list" :key="index" :secs="secs"></my-section>
</main>
</template>

<script>
import MySection from './../components/MySection'
import info from '@/data/info.js'

export default {
  data() {
    let list =  [
      {
        title: '专业技能',
        list: [
          {
            title: 'JavaScript',
            list: [
              'Lorem ipsum dolor sit amet consectetur adipisicing elit. Blanditiis, labore.',
              'Lorem ipsum dolor sit, amet consectetur adipisicing elit. Exercitationem nulla at inventore consequuntur obcaecati? Doloremque quo dignissimos excepturi error officiis!'
            ]
          },
          {
            title: 'HTML',
            list: [
              'Lorem ipsum dolor sit amet consectetur adipisicing elit. Blanditiis, labore.',
              'Lorem ipsum dolor sit amet consectetur adipisicing elit. Cumque id optio blanditiis? Iusto, velit quisquam.'
            ]
          },
          {
            title: 'others',
            list: [
              'Lorem ipsum dolor sit amet consectetur adipisicing elit. Sed rerum totam eos velit sit, earum, consectetur possimus odit maxime officiis vel provident soluta cumque optio dolor voluptate nulla molestiae delectus?',
              'Lorem, ipsum dolor sit amet consectetur adipisicing elit. Laboriosam facilis distinctio molestias harum saepe, molestiae voluptates vero eum tempore fugiat officia eos laudantium autem sit recusandae nulla minus? Possimus, veniam!',
              'Lorem ipsum dolor sit amet consectetur adipisicing elit. Veniam eveniet magnam suscipit atque, iure consequuntur rerum deserunt dolores aut nostrum corrupti fuga iusto impedit quos ratione. Harum magnam reprehenderit explicabo?'
            ]
          }
        ]
      },
      {
        title: '工作履历',
        list: [
          {
            title: '2018.04至今',
            list: [
              'Lorem ipsum dolor sit amet consectetur adipisicing elit.'
            ]
          },
          {
            title: '2017.05-2018.03',
            list: [
              'Lorem ipsum dolor sit amet.'
            ]
          }
        ]
      },
      {
        title: '项目经验',
        list: [
          {
            title: 'xxx项目',
            list: [
              {
                label: '项目描述',
                desc: [
                  'Lorem ipsum dolor sit amet consectetur adipisicing elit. ',
                  'Sunt quis repellendus aspernatur laudantium exercitationem incidunt, ',
                  'quidem recusandae ducimus blanditiis quisquam facilis odit porro dolorem quos officia tempora debitis veritatis fuga?'
                ].join('')
              },
              {
                label: 'Github地址',
                desc: 'github.com/xxx'
              }
            ]
          }
        ]
      },
    ];
    return {
      // list: info.mainInfo || list
      list
    }
  },
  components: {
    MySection
  }
}
</script>

<style lang="scss">

</style>
