<template>
<div>

    <div class="black-bg" v-if="글쓰기==true">
          <div class="white-bg">
            <useless/>
            <button class="attach-button" @click="첨부파일=true"> 첨부파일 </button>
              <div class="file-upload" v-if="첨부파일==true">
                <div>
                  <label for="avatar"></label>
                  <input type="file"
                  id="avatar" name="avatar"
                  accept="image/png, image/jpeg">
                </div>
                  <button @click="업로드=true"> 업로드 </button>
                <div v-if="업로드==true">
                  <h5>업로드가 완료되었습니다.</h5>
                </div>

              </div>
              <div>
                
              </div>
        <button class="close-button" @click="close">
           닫기

        </button>
        </div>
      </div>
    <div class="header">
        <img class="logo-img" src="../assets/logo.png" alt="사진" />

    </div>
    <div>
      <h1> nav </h1>
      <button @click="글쓰기=true"> 글쓰기 </button>


    </div>
    

    <div class="content">

    <Photo :data="data[0]" />
    <Photo :data="data[1]" />
    <Photo :data="data[2]" />

    </div>



</div>
</template>

<script>
// import Useless from './Useless.vue'
import Photo from './Photo.vue'
import Useless from './Useless.vue'
export default {
  name: 'HelloWorld',
  components : {Photo, Useless},
  props: {
  },
  data() {
    return {
      첨부파일 : false,
      글쓰기 : false,
      업로드 : false,
      message : '안녕하세요',
      counter : 0,
      inputMessage : '',
       data : [
        {
          img : '/dog.jpg',
          content : '멍멍이 1'
        },
        {
          img : '/cat.jpg',
          content : '야옹이 1'
        },
        {
          img : '/dog2.png',
          content : '멍멍이 2'
        },
        {
          img : '/cat2.jpg',
          content : '야옹이 2'
        },
      ],
      data2 : [
        {
          title : '제목1',
          msg : '안녕1',
        },
        {
          title : '제목2',
          msg : '안녕2',
        },
        {
          title : '제목3',
          msg : '안녕3',
        },
        {
          title : '제목4',
          msg : '안녕4',
        },
        {
          title : '제목5',
          msg : '안녕5',
        },
        {
          title : '제목6',
          msg : '안녕',
        },
        {
          title : '제목7',
          msg : '안녕7',
        }
      ]
    }
  },
  methods: {
    plus : function() {
      this.counter++;
    },
    minus : function() {
      this.counter--;
    },
    changeHello : function() {
      this.message = "반갑습니다."
    },
    change : function() {
      this.message = this.inputMessage
    },
    close : function() {
      this.첨부파일 = false
      this.글쓰기 = false
      this.업로드 = false
    }
  },
}


</script>

<style scoped>

.close-button {
  height: 41px;
  width: 60px;
  margin-bottom: 15px;
}

.attach-button {
  height: 41px;
  width: 100px;
  margin-top: 20px;
  margin-bottom: 10px;
}



body {
  margin : 0
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%;
  height: 100vh;
  background: rgba(0,0,0,0.5);
  position: fixed; 
  padding: 20px;
    top: 0px;
  }


 .white-bg {
 widows: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
  margin-top : 300px;
  }

  .file-upload {
  widows: 100%; background: pink;
      margin-top: 50px;
    margin-bottom: 50px;
  border-radius: 6px;
  padding: 50px;

  }
        * {
            padding : 0px;
            margin : 0px;
        }
        .header {
            height: 15vh;
        }

        .nav {
            height: 10vh;
        }

        .content {
            height: 75vh;
        }   

        .logo-img {
          width : 300px;
          float : left;
        }
</style>

