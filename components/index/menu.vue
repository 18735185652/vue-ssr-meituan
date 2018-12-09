<template>
  <div class="m-menu">
    <dl
      class="nav"
      @mouseleave="mouseleave">
      <dt>全部分类</dt>
      <dd
        v-for="(item,idx) in menu"
        :key="idx"
        @mouseenter="enter"
      >
        <i :class="item.type"/>{{ item.name }} <span class="arrow"/>
      </dd>
    </dl>
    <div
      v-if="kind"
      class="detail"
      @mouseenter="sover"
      @mouseleave="sout"
    >
      <template
        v-for="(item,idx) in curdetail.child">
        <h4 :key="idx">{{ item.title }}</h4>
        <span
          v-for="val in item.child"
          :key="val">{{ val }}</span>
      </template>

    </div>
  </div>
</template>
<script>
  export default{
    data(){
        return{
            kind:'',
            menu:[{
                type:"food",
                name:"美食",
                child:[{
                    title:'美食',
                    child:['代金券',"甜点","饮料","面包","自助餐"]
                }]
            },
              {
                type:"takeout",
                name:"外卖",
                child:[{
                  title:'外卖',
                  child:['饺子',"面条","大米","面包"]
                }]
              },
              {
                type:"hotel",
                name:"酒店",
                child:[{
                  title:'酒店星级',
                  child:['经济型',"舒适型","高档/四星","豪华/五星"]
                }]
              }]
        }
    },
    computed:{
        curdetail(){
            return this.menu.filter((item) => item.type===this.kind)[0];
        }
    },
    methods:{
      mouseleave(){
         this._timer = setTimeout(()=>{
              this.kind='';
          },150)
      },
      enter(e){
          this.kind = e.target.querySelector("i").className;
      },
      sover(){
          clearTimeout(this._timer)
      },
      sout(){
        this.kind = ''
      }

    }
  }
</script>
<style lang="scss">

</style>
