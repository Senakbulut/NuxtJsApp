 <template>
     <div>
     <h3>Customer Reviews</h3>
     <div>
        <ReviewCard
        v-for="review in reviewers.results"
        :key="review.login.uuid"
        :review="review"
        />
     </div>
     </div>
 </template>
 
 <script>
     export default {
         data() {
             return{
                 reviewers: []
             }
         },
         async fetch() {
             this.reviewers = await fetch(
                 'https://randomuser.me/api/?results=5'
             ).then(res=>res.json())
         }
     }
 </script>
 
 <style  scoped>
 
 </style>