<template>
    <input
        type="checkbox"
        :value="value"
        v-model="proxyChecked"
        class="w-6 h-6 border border-darkGray text-lightBlue focus:border-lightBlue focus:ring focus:ring-darkBlue focus:ring-opacity-50"
    />
</template>

<script>
    export default {
        emits: ["update:checked"],

        props: {
            checked: {
                type: [Array, Boolean],
                default: false,
            },
            value: {
                default: null,
            },
        },

        computed: {
            proxyChecked: {
                get() {
                    return this.checked;
                },

                set(val) {
                    this.$emit("update:checked", val);
                },
            },
        },
    };
</script>
