<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link href="https://fonts.googleapis.com/icon?family=Material+Icons"
      rel="stylesheet">

    <title>Document</title>
    <style>
        body{
            margin: 0;
            padding: 0;
            font-family: Arial, Helvetica, sans-serif;
            box-sizing: border-box;
            overflow-x: hidden;
            position: relative;
        }

nav{
    display: flex;
    justify-content: space-between;
    background-color: chocolate;
    position: fixed;
    width: 100%;
    align-items: center;
    z-index: 111;
}
nav ul{
    list-style: none;
    display: flex;
    width: 30%;
    justify-content:space-evenly ;
    text-decoration: none;
}
nav h2{
padding-left: 5px;
}
a{
    text-decoration: none;
    color: black;
}
a:hover{
    color: white;
}
.gas{
    position: relative;
}
.gas::after{
    content: '';
    display: block;
    position: absolute;
    width: 50%;
    height: 2px;
    background-color: blue;
    top: 20px;
    left: 10px;
    right: 10px;
    transform: scale(0);
    transition: all 100ms;
    
}
.gas:hover::after{
transform: scale(1);
}
.togle{
display: none;
position: relative;
flex-direction: column;
justify-content: space-between;
height: 25px;
}
.togle input{
    position: absolute;
    top: -5px;
    right: 15px;
    width: 30px;
    height: 30px;
    z-index: 22;
    cursor: pointer;
    opacity: 0;
}
.togle span{
   display: block;
width: 28px;
height: 5px;
background-color: aqua;
border-radius: 5px;
margin-right: 20px;
transition: all .5s;
}
.togle span:nth-child(2){
    
    z-index: 1;
    transform: translate(0,0);
}
.togle span:nth-child(4){
    transform: translate(0,0);
}
.togle input:checked~span:nth-child(2){
    transform: rotate(45deg) translate(8px ,5px);
}
.togle input:checked~span:nth-child(4){
    transform: rotate(-45deg) translate(10px ,-5px);
}
.togle input:checked~span:nth-child(3){
    transform: scale(0);
}
.jumbotron{
    text-align: center;
    background-size: cover;
    background-image: url(back.png);
    background-repeat: no-repeat;
    background-position: center;
    height: 70vh;
}
.jumbotron img{
    border-radius: 50%;
    border: 5px solid rgb(177, 175, 175);
    margin-top: 100px;
    margin-bottom: 0;
}
.jumbotron h1{
    margin-top: 0;
    margin-bottom: 0;
    font-size: 50px;
    color: rgb(202, 199, 199);
    font-family: 'Courier New', Courier, monospace;
text-shadow: 0px 2px 2px rgba(0, 0, 0, 0.5) ;
}
.jumbotron p{
margin-top: 5px;
font-size: 20px;
color: rgb(202, 199, 199);
text-shadow: 0px 2px 2px rgba(0, 0, 0, 0.3) ;
}
.about{
    display: grid;
    justify-content: space-around;
    grid-template-columns: 1fr 50px 1fr;
    grid-template-areas: 
    'judul judul judul'
    'teks1 teks2 teks2';
}
.judul{
    grid-area: judul;
    display: flex;
    text-transform: uppercase;
    justify-content:center ;
    grid-column-start: 1;
    grid-column-end: -1;
}
.teks1 p{
    text-align: end;
  grid-area: teks1;
    padding-left: 100px;
    opacity: 0;
    animation: animasi 1s ease forwards;
}
.teks1 {
    transform-origin: 0 0;
}
.teks2 {
   
    transform-origin: 0 0;
}
.teks2{
    grid-area: teks2;
    padding-right: 100px;
    grid-column-start: 3;
    grid-column-end: 4;
  
}
.teks2 p{
text-align: start;
animation: animasi2 1s ease forwards
}

.profil{
    display: grid;
    grid-template-columns: 1fr;
   
}
.profil .picture img{
    display: block;
    width: 100%;
}
.txtprofil{
    display: flex;
    justify-content: center;
    grid-column-start: 1;
    grid-column-end: -1;
}
.picture{
    display: grid;
    width: 50%;
    margin: 20px auto;
    grid-template-columns: repeat(auto-fit, minmax(200px,1fr));
    column-gap: 5px;
    row-gap: 5px;
}
.picture img{
    transition: all .5s;
    cursor: pointer;
}
.picture img:hover{
    margin-top: 0px;
    box-shadow: 0 2px 2px rgba(0, 0, 0, 0.5);

}
.bungkus{
    position: relative;
}
.overlay{
    display: none;
    position: fixed;
    top: 0;
    bottom: 0;
    width: 100%;
    height: auto;
    justify-content: center;
    background-color: rgba(0,0,0,0.7);
}
.overlay .close{
   
    width: 30px;
    height: 30px;
    margin-top: 70px;
    margin-right: 10px;
    filter: drop-shadow(0 2px 2px rgb(173, 171, 171));

}
.overlay:target{
    display: flex;
}
.contact{
    display: grid;
    margin: 20px auto;
    justify-content: center;
    font-size: 18px;
    text-transform: uppercase;
    background-color: gray;
    grid-template-columns: 1fr 1fr;
}
.teksC{
display: flex;
    justify-content: start;
    grid-column-start: 1;
    grid-column-end: -1;
}
.form{
    display: flex;
    justify-content: center;
    grid-column-start:-3;
    grid-column-end: -1;
    box-sizing: border-box;
    padding-bottom: 10%;

}
.inp{
    display: block;
    width: 550px;
    padding: 10px;
    border-radius: 5px;
    margin: 9px auto;
    border: 2px solid transparent;

    
}
.inp.sel{
    width: 575px;
    cursor: pointer;
}
.inp:focus{
    outline: none;
    border: 2px solid lightblue;
    transition: 1s;
}
.pes:focus{
    outline: none;
    border: 2px solid lightblue;
    transition: 1s;
}
footer{
    background-color: rgb(236, 177, 134);
    width: 100%;
    height: 70px;
    margin-top:-20px ;
    text-align: center;
    font-style: italic;
}
footer h3{
    padding-top: 20px;
}
@media screen and (max-width:576px) {
nav ul{
  
    justify-content: space-evenly;
    right: 0;
    top: 50px;
    align-items: center;
    flex-direction: column;
    position: absolute;
    width: 100%;
    height: 200px;
    transform: translate(100%);
}
.togle{
    display: flex;
}
.togle input:checked~,ul{
    transform: translate(0);
}
.teks1 {
    display: flex;
    justify-content: center;
    grid-column-start: 1;
    grid-column-end:4 ;

} 
.teks1 p{
    text-align: center;
    padding: 0 7%;
    animation: animasi3 2s ease forwards;
}
.teks2 {
    display: flex;
    justify-content: center;
    grid-column-start: 1;
    grid-column-end:4 ;
    padding-right: 0;

} 
.teks2 p{
    text-align: center;
    padding: 0 7%;
    animation: animasi4 2s ease forwards;
}
.about{
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-areas: 
    'judul judul judul'
    'teks1 teks1 teks1'
    'teks2 teks2 teks2';
}
.inp{
    width: 350px;
    margin: 9px 0;
}
.inp.sel{
    width: 370px;
}
.pes{
    width: 360px;
}
}
@keyframes animasi {
    0%{
transform: rotate(45deg);
    }
    100%{
        opacity: 1;
        transform: rotate(0deg);
    }
    
}
@keyframes animasi2 {
    0%{
transform:translate(50px) rotate(-45deg);
    }
    100%{
        opacity: 1;
        transform:translate(0px) rotate(0deg);
    }
    
}
@keyframes animasi3 {
    0%{
transform: translate(-100%);
    }
    100%{
        opacity: 1;
        transform: translate(0%);
    }
    
}
@keyframes animasi4 {
    0%{
transform: translate(100%);
    }
    100%{
        opacity: 1;
        transform: translate(0%);
    }
    
}

    </style>
</head>
<body>
    <nav>
       <a href="#"><h2>Syahroni</h2></a> 
        <ul>
            <a href=""><li class="gas">home</li></a>
            <a href=""><li class="gas">Profil</li></a>
            <a href=""><li class="gas">About</li></a>
            <a href=""><li class="gas">Contact</li></a>
        </ul>
        <div class="togle">
            <input type="checkbox" name="" id="">
            <span></span>
            <span></span>
            <span></span>
        </div>
    </nav>
    <div class="jumbotron">
        <img src="syahroni.png" alt="">
        <h1>Syahroni</h1>
        <p>Mahasiswa | Unindra</p>
    </div>
    <div class="about">
        <div class="judul">
        <h1>about</h1>
    </div>
    <div class="teks1">
        <p >Lorem ipsum dolor sit amet consectetur adipisicing elit. Nulla quos similique commodi, enim repudiandae, non rerum cumque nihil aperiam quam consequuntur dolor excepturi? Eum obcaecati vel dolorum at quaerat maiores veniam, nesciunt, sapiente odio dignissimos quibusdam suscipit molestias aut? Dignissimos soluta id corrupti aliquam culpa dicta pariatur sit cum amet, veniam eveniet, consequatur porro totam tenetur ipsum sint perspiciatis quae ullam explicabo corporis ex alias impedit labore? Corrupti, consequuntur alias!</p>
    </div>
 <div class="teks2">
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Magni, voluptates. Natus quibusdam numquam dolores voluptatum labore aliquam iste, odit, sunt ducimus harum molestiae. Aut neque ullam repudiandae minus, modi, molestias eius obcaecati repellendus nemo excepturi mollitia quidem velit placeat ex eum fuga nesciunt doloribus dignissimos praesentium suscipit. Voluptates, quo. Laudantium blanditiis nisi culpa. Esse consectetur quibusdam consequatur voluptatum accusantium, consequuntur repellat sit rem aut commodi quasi tempore, atque maxime impedit?</p>

    </div>
    </div>
    <div class="bungkus">
    <div class="profil" id="profil">
        <div class="txtprofil"><h1>My Profil</h1></div>
        <div class="picture">
        <a href="#foto1"><img src="syahroni.png" alt=""></a>
        <a href="#foto2"><img src="syahroni.png" alt=""></a>
        <a href="#foto3"><img src="syahroni.png" alt=""></a>
        <a href="#foto4"><img src="syahroni.png" alt=""></a>
        <a href="#foto5"><img src="syahroni.png" alt=""></a>
        <a href="#foto6"><img src="syahroni.png" alt=""></a>
       
    </div>
    </div>
    <div class="overlay" id="foto1">
        <a href="#profil"><img src="close.png" alt="" class="close"></a>
        <img src="syahroni.png" alt="">
    </div>
    <div class="overlay" id="foto2">
        <a href="#profil"><img src="close.png" alt="" class="close"></a>
        <img src="syahroni.png" alt="">
    </div>
    <div class="overlay" id="foto3">
        <a href="#profil"><img src="close.png" alt="" class="close"></a>
        <img src="syahroni.png" alt="">
    </div>
    <div class="overlay" id="foto4">
        <a href="#profil"><img src="close.png" alt="" class="close"></a>
        <img src="syahroni.png" alt="">
    </div>
    <div class="overlay" id="foto5">
        <a href="#profil"><img src="close.png" alt="" class="close"></a>
        <img src="syahroni.png" alt="">
    </div>
    <div class="overlay" id="foto6">
        <a href="#profil"><img src="close.png" alt="" class="close"></a>
        <img src="syahroni.png" alt="">
    </div>
</div>
    <div class="contact">
        <div class="teksC">
        <h1>Contact Me</h1>
    </div>
       <div class="form">
            <table>
                <tr>
                <td>
                    <label for="nama">Nama</label><br>
                    <input type="text" placeholder="Masukkan Nama" class="inp">
                </td>
            </tr>
            <tr>
                <td>
                    <label for="email">Email</label><br>
                    <input type="email" name="email" id="" placeholder="Masukkan Email" class="inp">
                </td>
            </tr>
            <tr>
                <td>
                    <label for="telp">Nomor Telpon</label><br>
                    <input type="number" name="" id="" placeholder="Masukkan Nomor Telepon" class="inp">
                </td>
            </tr>
            <tr>
                <td>
                    <label for="kategori">Kategori</label>
                    <br>
                    <select name="kategori" id="" class="inp sel">
                        <option value="">HTML</option>
                        <option value="">CSS</option>
                        <option value="">Javascript</option>
                    </select>
                </td>
            </tr>
            <tr>
                <td>
                    <label for="pesan">Masukkan Pesan</label><br>
                    <textarea name="" id="" cols="78" rows="10" placeholder="Masukkan Pesan" class="pes"></textarea>
                </td>
            </tr>
            </table>
        </div>
    </div>
    <footer>
<h3>&copy; Copyright By Syahroni | 2022</h3>
    </footer>
</body>
</html>
