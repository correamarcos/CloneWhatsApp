<template>
    <div class="balloon" :class="{verde: verde}">
        {{conteudo}}
        <span>{{horario}}</span>
    </div>
    
</template>
<script>

export default{
    props: ['conteudo', 'horario', 'verde']
}

</script>