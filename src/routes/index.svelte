<script lang = 'ts'>
    
    import MyButton from './myButton.svelte';
    var emoji = ('❤️');
let imags = ["Work", 'Work-1', 'Work-2'];
let sbars = ['my process', 'client reviews', 'download cv'];
    


</script>



<MyButton/>
<div class="welMes">
    <h1>
        hello there, nice to meet you {emoji}, i am
    </h1>
</div>
<div class= 'lkami'>
    <h1>
        kamilia
    </h1>
</div>
<div class='lots'>
    <h2>
        Whether article spirits new her covered hastily sitting
        her. Money witty books nor son add. Chicken age had
        evening believe but proceed pretend mrs.
    </h2>
</div>
    <div class= 'latest'>
        <h1>
        Latest Work
        </h1>
    </div>
    <div class= 'work'>
       {#each imags as pic} 
        <img src= './Workpics/{pic}.png' alt= '{pic}' />
       {/each}
    </div>
    <div class="view">
        <h3>
            view all
        </h3>
    </div>
    <div class="pink">
    </div>

    <div class = 'large'>
        <img src= './largePic/Hero Image.png' alt= 'Hero Image'/>
    </div>
    <div class = 'big'>
        <div class = 'sidebar'>
            {#each sbars as bar}
           <p>
            {bar}
           </p>
            {/each}
        </div>
    </div>

<style>
    .welMes{
        display : flex;
        flex-direction: row;
        justify-content: flex-start;   
    }
    .welMes{
        margin-left :3rem;
        position: absolute;
        width: 500px;
        height: 28px;
        margin-left: 5rem;
        top: 205px;

        font-family: Google Sans;
        font-style: normal;
        font-weight: normal;
        font-size: 10px;
        line-height: 28px;
        letter-spacing: 0.06em;
        text-transform: uppercase;

        color:#444444;
    }
    .lkami{
        position: absolute;
        width: 499px;
        height: 203px;
        left: 86px;
        top: 140px;

        font-family: Abhaya Libre ExtraBold;
        font-style: normal;
        font-weight: 800;
        font-size: 95px;
        line-height: 203px;
        letter-spacing: -0.04em;
        color: #CB3322;
    }
    .lots{
        position: absolute;
        width: 570px;
        height: 90px;
        left: 94px;
        top: 490px;

        font-family: Google Sans;
        font-style: normal;
        font-weight: normal;
        font-size: 15px;
        line-height: 30px;
        color: #505050;

    }
    .latest{
        position: absolute;
        width: 600px;
        height: 63px;
        left: 95px;
        top: 680px;

        font-family: Circular Std;
        font-style: normal;
        font-weight: 900;
        font-size: 30px;
        line-height: 63px;

        color: #000000;
    }
    .work{
        display:flex;
        flex-direction: row;
        align-items: left;
        position: absolute;
        width: 718px;
        height: 163px;
        left: 94px;
        top: 830px;
    }
    .view{
        position: absolute;
        width: 70px;
        height: 20px;
        left: 6rem;
        top: 1000px;
        bottom: 90%;

        font-family: Sofia Pro;
        font-style: normal;
        font-weight: normal;
        font-size: 15px;
        line-height: 20px;
        color: #CB3322;
    
    }
    .pink{
        position: absolute;
        width: 390px;
        height: 594px;
        left: 249px;
        top: -130px;
        z-index: -5;

        background: #FFE6E4;
    }
    .large{
        position: absolute;
        width: 565px;
        height: 880px;
        left: 720px;
        top: 114px;
        z-index: -5;
    }
    .sidebar{
        position: absolute;
        display:flex;
        flex-direction: row;
        justify-content: space-between;
        display: flex;
        flex-direction: row;
        align-items: flex-start;
        padding: 0px;
       
        position: absolute;
        width: 350px;
        height: 450px;
        left: 1330px;
        top: 600px;
        
        transform: rotate(-90deg); 
       
    }
    .sidebar > p {
      font-weight: bold;
      font-size: 18px;
      transition: all 0.2s; 
    }
    p:hover{
        transform: scale(1.1);
        cursor: pointer;
        color:#CB3322;
       
    }
    h3:hover{
        text-decoration: underline;
        cursor: pointer;
    }
   
</style>
