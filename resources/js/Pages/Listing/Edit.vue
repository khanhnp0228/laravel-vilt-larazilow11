<template>
    <form @submit.prevent="update">
        <div>
            <div>
                <label>Beds</label>
                <input type="text" v-model.number="form.beds" />
                <div v-if="form.errors.beds" class="errors-display">
                    {{ form.errors.beds }}
                </div>
            </div>

            <div>
                <label>Baths</label>
                <input type="text" v-model.number="form.baths" />
                <div v-if="form.errors.baths" class="errors-display">
                    {{ form.errors.baths }}
                </div>
            </div>

            <div>
                <label>Area</label>
                <input type="text" v-model.number="form.area" />
                <div v-if="form.errors.area" class="errors-display">
                    {{ form.errors.area }}
                </div>
            </div>

            <div>
                <label>City</label>
                <input type="text" v-model="form.city" />
                <div v-if="form.errors.city" class="errors-display">
                    {{ form.errors.city }}
                </div>
            </div>

            <div>
                <label>Post Code</label>
                <input type="text" v-model="form.code" />
                <div v-if="form.errors.code" class="errors-display">
                    {{ form.errors.code }}
                </div>
            </div>

            <div>
                <label>Street</label>
                <input type="text" v-model="form.street" />
                <div v-if="form.errors.street" class="errors-display">
                    {{ form.errors.street }}
                </div>
            </div>

            <div>
                <label>Street Nr</label>
                <input type="text" v-model.number="form.street_nr" />
                <div v-if="form.errors.street_nr" class="errors-display">
                    {{ form.errors.street_nr }}
                </div>
            </div>

            <div>
                <label>Price</label>
                <input type="text" v-model.number="form.price" />
                <div v-if="form.errors.price" class="errors-display">
                    {{ form.errors.price }}
                </div>
            </div>

            <div>
                <button type="submit"> Update </button>
            </div>

        </div>
    </form>
</template>

<script setup>
import { useForm } from '@inertiajs/vue3';
import { reactive } from 'vue'

const props = defineProps({
    listing: Object,
})

const form = useForm({
    beds: props.listing.beds,
    baths: props.listing.baths,
    area: props.listing.area,
    city: props.listing.city,
    code: props.listing.code,
    street: props.listing.street,
    street_nr: props.listing.street_nr,
    price: props.listing.price,

});

const update = () => form.put(route('listing.update', {listing: props.listing.id}), form)

</script>

<style scoped>
label {
    margin-right: 2em;
}

div {
    padding: 2px;
}

.errors-display {
    color: #ff0000;
}
</style>
