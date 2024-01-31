<script setup>
import { Client } from '@notionhq/client' 
//const { Client } = require("@notionhq/client");

// Initializing a client
const notion = new Client({
  auth: "secret_HOa5UpkTWIiIYiCSAD75ikyTzy4Lof6cd5l78QaD0I2",
});

async function fetchData() {
  
  try {
      const notionData = await notion.databases.query({
        database_id: '42c3642bc808464a81aefd349f73a02e',
        filter_properties: []
      });
      return notionData.results;
    } catch (error) {
      console.error('Error fetching Notion data:', error.message);
      throw error;
    }
  

    /*
    try {
    // /api 부분이 요청 도메인인 https://api.allsilver.com/ 로 치환되므로
    // CORS를 회피할 수 있다.
    const res = await fetch('/api/v1/databases/42c3642bc808464a81aefd349f73a02e/query', {
      method: 'POST',

      headers: {
        'Authorization': 'Bearer secret_HOa5UpkTWIiIYiCSAD75ikyTzy4Lof6cd5l78QaD0I2',
        'Notion-Version': '2022-06-28',
        'Content-Type': 'application/json'
      },
    })
    

    if (!res.ok) {
      throw new Error(`API Call Fail: ${res}`)
    }
    return await res.json()
  } catch (e) {
    if (e instanceof Error) {
      console.error(e.message)
    } else {
      alert('An unexpected error occurred')
    }
  }
  */
}



console.log(fetchData())
</script>

<template>

</template>

<style scoped>

</style>
