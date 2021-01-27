<template>
    <div class="container">
        <a-button type="primary"> 1 </a-button>
        <a-button type="dashed"> 1 </a-button>
        <a-button type="danger" shape="circle" icon="search"></a-button>
        <a-button type="danger" shape="circle" loading></a-button>
        <a-button type="danger" shape="link" size="large" icon="download"></a-button>
        <a-icon type="global" />
        <a-button type="primary">Button</a-button>
        <div>
            <a-upload>
                <a-button> <a-icon type="upload" /> Click to Upload </a-button>
            </a-upload>
            <a-popconfirm title="Are you sure delete this task?" ok-text="Yes" cancel-text="No">
                <a-button>Confirm</a-button>
            </a-popconfirm>
        </div>
          
        
        

    </div>


</template>

<script>

    export default {

        data() {
            return {

            }
        },
        methods: {

        }

    }
</script>

<style lang="less" scoped>



</style>