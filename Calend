<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Calendário</title>

<style>
body{
    font-family:Arial,sans-serif;
    background:#1e1e2f;
    color:white;
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
    margin:0;
}

.calendario{
    width:360px;
    background:#2b2b3d;
    padding:20px;
    border-radius:15px;
    box-shadow:0 0 15px rgba(0,0,0,.4);
}

.topo{
    display:flex;
    justify-content:space-between;
    align-items:center;
    margin-bottom:20px;
}

button{
    background:#4caf50;
    color:white;
    border:none;
    padding:8px 12px;
    border-radius:8px;
    cursor:pointer;
}

button:hover{
    background:#43a047;
}

.dias-semana,.dias{
    display:grid;
    grid-template-columns:repeat(7,1fr);
    gap:8px;
}

.dias-semana div{
    text-align:center;
    font-weight:bold;
}

.dias div{
    text-align:center;
    padding:12px;
    border-radius:8px;
}

.dias div:hover{
    background:#4caf50;
    cursor:pointer;
}

.hoje{
    background:#2196f3;
}
</style>
</head>
<body>

<div class="calendario">
    <div class="topo">
        <button onclick="mudarMes(-1)">◀</button>
        <h2 id="mesAno"></h2>
        <button onclick="mudarMes(1)">▶</button>
    </div>

    <div class="dias-semana">
        <div>Dom</div>
        <div>Seg</div>
        <div>Ter</div>
        <div>Qua</div>
        <div>Qui</div>
        <div>Sex</div>
        <div>Sáb</div>
    </div>

    <div class="dias" id="dias"></div>
</div>

<script>
const meses=[
"Janeiro","Fevereiro","Março","Abril","Maio","Junho",
"Julho","Agosto","Setembro","Outubro","Novembro","Dezembro"
];

let data=new Date();

function desenhar(){
    const dias=document.getElementById("dias");
    dias.innerHTML="";

    const ano=data.getFullYear();
    const mes=data.getMonth();

    document.getElementById("mesAno").innerText=
    meses[mes]+" "+ano;

    const primeiro=new Date(ano,mes,1).getDay();
    const ultimo=new Date(ano,mes+1,0).getDate();

    for(let i=0;i<primeiro;i++){
        dias.innerHTML+="<div></div>";
    }

    const hoje=new Date();

    for(let d=1;d<=ultimo;d++){
        const div=document.createElement("div");
        div.innerText=d;

        if(
            d===hoje.getDate() &&
            mes===hoje.getMonth() &&
            ano===hoje.getFullYear()
        ){
            div.classList.add("hoje");
        }

        dias.appendChild(div);
    }
}

function mudarMes(valor){
    data.setMonth(data.getMonth()+valor);
    desenhar();
}

desenhar();
</script>

</body>
</html>
