<template>
    <hr>
    <div  class="container p-4 m-4">
    <h2 v-if="isDisplay">Show table</h2>
    <h2 v-else>Not Show table</h2>
    <template  v-if="isDisplay" >
        <table class="table table-striped" :class="className">
            <thead>
                <tr>
                <th scope="col">#</th>
                <th scope="col">First</th>
                <th scope="col">Last</th>
                <th scope="col">Handle</th>
                </tr>
            </thead>
            <tbody>
                <template v-for="(info, key) in infos" :key="key">
                    <tr>
                        <th scope="row">{{ key+1 }}</th>
                        <td>{{ info.name }}</td>
                        <td>{{ info.age }}</td>
                        <td>{{ info.occ }}</td>
                    </tr>
                </template>
            </tbody>
        </table>
    </template>
    </div>
</template>

<script>
export default{
    data(){
            return {
                isDisplay : true,
                className : 'zunaid' ,
                names : ['Zunaid', 'Tithy', 'Mim', 'Sadia', 'Ayesha'],
                infos : [
                    {name:'Zunaid',age: 25, occ:"Software"},
                    {name:'Tithy', age:25, occ:"Software"},
                ],
            }
        },
}

</script>

<style>
    .table{
        padding:10px 10px !important;
    }
</style>