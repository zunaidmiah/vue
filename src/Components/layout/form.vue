<template>
    <hr />
    <div class="container p-4 m-4">
        <pre>
            {{ JSON.stringify(formData, null, 2) }}
        </pre>
        <form @submit.prevent="submitForm">
            <div class="form-group">
                <label for="exampleFormControlInput1">Full Name</label>
                <input type="text" class="form-control" id="exampleFormControlInput1" @keyup.tab="keyUp" placeholder="John Doe.." v-model.trim="formData.name"/>
            </div>

            <div class="form-group">
                <label for="exampleFormControlInput2">Email address</label>
                <input type="email" class="form-control" id="exampleFormControlInput2" placeholder="name@example.com"  v-model="formData.email"/>
            </div>

            <div class="form-group">
                <label for="exampleFormControlSelect1">Example select</label>
                <select class="form-control" id="exampleFormControlSelect1"  v-model="formData.singleSelect">
                    <option>1</option>
                    <option>2</option>
                    <option>3</option>
                    <option>4</option>
                    <option>5</option>
                </select>
            </div>

            <div class="form-group">
                <label for="exampleFormControlSelect2">Example multiple select</label>
                <select multiple class="form-control" id="exampleFormControlSelect2"  v-model="formData.multipleSelect">
                    <option>1</option>
                    <option>2</option>
                    <option>3</option>
                    <option>4</option>
                    <option>5</option>
                </select>
            </div>

            <div class="form-group">
                <label for="exampleFormControlTextarea1">Example textarea</label>
                <textarea class="form-control" id="exampleFormControlTextarea1" rows="3"  v-model="formData.textArea"></textarea>
            </div>

            <div class="form-check form-check-inline">
                <input class="form-check-input" type="checkbox" id="inlineCheckbox1" value="option1"  v-model="formData.radioButton"/>
                <label class="form-check-label" for="inlineCheckbox1">1</label>
            </div>
            <div class="form-check form-check-inline">
                <input class="form-check-input" type="checkbox" id="inlineCheckbox2" value="option2"  v-model="formData.radioButton"/>
                <label class="form-check-label" for="inlineCheckbox2">2</label>
            </div>
            <div class="form-check form-check-inline">
                <input class="form-check-input" type="checkbox" id="inlineCheckbox3" value="option3"  v-model="formData.radioButton"/>
                <label class="form-check-label" for="inlineCheckbox3">3</label>
            </div>

            <div class="form-group my-4">
                <button class="btn btn-primary">Submit</button>
            </div>
        </form>
    </div>
    <hr />
</template>

<style></style>

<script>
export default {
    data() {
        return {
            formData: {
                name: "",
                email: "",
                singleSelect: "",
                multipleSelect: [],
                textArea: "",
                radioButton: []
            },
        };
    },

    methods: {
        submitForm(event){
            // event.preventDefault();
            console.log(this.formData)
        },
        keyUp(){
            alert("keyUp now");
        }
    }
};
</script>
