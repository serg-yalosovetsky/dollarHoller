<script lang="ts">
    export let label: 'draft' | 'sent' | 'current' | 'late' | 'paid' = 'draft';
</script>


<div class="text-md w-20 rounded-full text-center font-bold capitalize text-pastelPurple border-pastelPurple border-1"
    class:inverted={label === "draft"}
    class:success={label === "sent" || label === "current"}
    class:alert={label === "late"}
    class:arcive={label === "paid"}
    >
    {label}
</div>

<style lang="postcss">
    .inverted {  
        @apply border-pastelPurple text-pastelPurple;
    }

    .success {
        @apply border-robinEggBlue bg-robinEggBlue text-blueGem;
    }

    .alert {
        @apply border-scarlet bg-scarlet text-goldenFizz;
    }

    .arcive {
        @apply border-pastelPurple bg-pastelPurple text-white;
    }
</style>