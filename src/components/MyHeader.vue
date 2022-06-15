<template>
    <div class="navbar">
        <h2>{{logo}}</h2>
        <MyConnectWalletVue />
    </div>
    <div class="header">
        <div class="header_left">
            <h1>Digital NFT Sneakers</h1>
            <p>30 one-of-a-kind HypeSneakrs on the Ethereum Blockchain, programmatically generated using the HypeFactory rarity algorithm.</p>

            <button class="buttonMint" @click="toggleModal">NFT Mint</button>
            
            <div v-if="showModal" class="psab">
                <MyModal @close="showModal"/>
            </div>
        </div>
        <div class="header_right">
            <img src="https://hypesneakrs.com/CoverGif.gif" alt="">
        </div>
    </div>
</template>


<script>
import MyConnectWalletVue from './MyConnectWallet.vue'
import MyModal from './MyModal.vue'
export default{
    props: ['logo'],
    components: { MyConnectWalletVue, MyModal },
    data(){
        return{
            showModal: false
        }
    },
    methods: {
        toggleModal(){
            this.showModal = !this.showModal
        }
    }
}
</script>

<style extends>
    .navbar{
        width: 100vw;
        height: 40px;
        background-color: black;
        padding: 12px 25px 5px;
        color: white;
        display: flex;
        justify-content: space-around;
    }
    .navbar > h2{
        padding: 0;
        margin: 0;
        font-size: 27px;
    }
    .header{
        display: flex;
        justify-content: space-around;
        padding: 150px 20px 0 20px;
    }
    .header_left{
        width: 430px;
    }
    .header_left > h1{
        font-size: 40px;
        margin-bottom: 40px;
    }
    .header_left > p{
        font-size: 25px;
    }
    .header_right {
        width: 400px;
        height: 400px;
    }
    .header_right > img{
        width: 100%;
        height: 400px;
    }
    .header_left > .buttonMint{
        width: 390px;
        height: 45px;
        cursor: pointer;
        font-weight: 900;
        background-color: black;
        color: white;
        border: 2px solid white;
        
    }
    .buttonMint:hover{
        background-color: white;
        color: black;
        border: 1px solid black;
    }
</style>