<template>
    <div class="d-flex mt-4 ml-3" >
        <div class="card p-3 mr-4" style="width: 18rem;" v-for="(bote , index) in dataStudent" :key="index">
          <div>
            <p>{{bote.nama}}</p>
            <p>{{bote.deskripsi_diri}}</p>
            <table class="" width="100%">
            <tr>
                <td>Email </td>
                <td>:{{bote.email}}</td>
                <td width="5%"></td>
                <td></td>
            </tr>
            <tr>
                <td>Soft Skill</td>
                <td>:{{bote.soft_skill}}</td>
                <td></td>
                <td></td>
            </tr>
            <tr>
                <td>Hard Skill</td>
                <td>:{{bote.hard_skill}}</td>
                <td></td>
                <td></td>
            </tr>
            <tr>
                <td>Interest</td>
                <td>:{{bote.interest}}</td>
                <td></td>
                <td></td>
            </tr>
            <tr> 
                <td>
                    <router-link :to="{ name:'botekuat', params: { id: bote.id }}" class="btn btn-sm btn-warning">Update</router-link>
                </td>
                
                <td>
                    <button class="btn btn-sm btn-danger" @click="deleteStudentFunc(bote.id)">Delete</button>
                </td>             
                <td><img src="../assets/female.png" width="30px" v-show="bote.jenis_kelamin == 'Female'"></td>
                <td><img src="../assets/male.png" width="30px" v-show="bote.jenis_kelamin == 'Male'"></td>
            </tr>                    
        </table>
          </div>
          
        </div>
    </div>
</template>

<script>
import addService from '../services/addService';
// import SuccesForm from '../components/SuccesForm.vue';
export default {
    name: 'ProjectVueCardComp',

    methods: {
        getData(){
            addService.getAll()
            .then(response => {
                this.dataStudent = response.data;
                // console.log(this.dataStudent);
            })
            .catch(e => {
                console.log(e);
            });
        },
        deleteStudentFunc(id){
            if(confirm("Apakah anda yakin ingin hapus")){
                addService.deleteStudent(id).then(response => {
                    console.log(response.data);
                })
                .catch(e => {
                    console.log(e);
                });
                location.reload();
            }else{
                alert("Hapus dibatalkan!")
            }
        }
    },

    mounted() {
        this.getData();
    },

    data() {
        return {
          dataStudent: null,  
        };
    },
    components: {
        // SuccesForm
    }

};
</script>

<style lang="scss" scoped>

</style>