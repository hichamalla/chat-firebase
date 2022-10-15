<script>
import { onMounted, ref } from 'vue';
import {db} from '../config/config'

import { collection, getDocs } from '@firebase/firestore';

export default{
  name:'homeView',
  setup(){
    const data=ref();
    onMounted(
      async ()=> {
        let docsRef = collection(db,'posts')
        let docs =await getDocs(docsRef)
        docs.forEach(doc=>{
          console.log(doc.data())
        })
      }
    )
  }
}
</script>

<template>

</template>
