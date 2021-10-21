# Calc
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    
    <title>Calculadora</title>
    <style>
        *{
            margin: 0;
            padding: 0;
        }
        .fundo{
           background-image: linear-gradient(45deg, black, crimson); 
           height: 100vh;
           color: white;
           font-family: Arial, Helvetica, sans-serif;
           text-align: center;
        }
        .Calculadora{
            border: 4px solid;
            border-image: linear-gradient(135deg,
            #FF0000 0%,
            #FF00A8 100%) 1; 
            position: absolute;
            background-color: rgba(0, 0, 0,0.8);
            top: 50%;
            left: 50%;
            transform: translate(-50%,-50%);
            border-radius: 15px;
         padding: 15px;   
        }
        .botao{
            width: 50px;
            height: 50px;
            font-size: 25px;
            margin: 3px;
            cursor: pointer;
            background-color: rgb(31,31,31);
            border: none;
            color: #fff;
        }
        .botao:hover{
            background-color: black;

        }
        #resultado{
            width: 207px;
            background-color: white;
            height: 30px;
            margin: 5px;
            font-size: 25px;
            text-align: right;
            padding: 5px;
            color: black;
        }
        .text{
            display: inline-block;
            color: transparent;
            background-image: linear-gradient(
                90deg, #fc87da 0%, #cb94ef 36%, #41e0e7 70%, #28f6c2 100%
            );
            -webkit-background-clip: text;
            background-clip: text ;
        }
        
    </style>
</head>
<body>
    <div class="fundo">
        <h1 class="text">Sávio Santos</h1>
        <div class="Calculadora">
            <h1 class="text">Calculadora</h1>
            <p id="resultado"></p>
            <table>
                <tr>
                    <td><button class="botao" onclick="clean()">C</button></td>
                    <td><button class="botao" onclick="back()"><</button></td>
                    <td><button class="botao" onclick="insert('/')">/</button></td>
                    <td><button class="botao" onclick="insert('*')">x</button></td>
                </tr>
                <tr>
                    <td><button class="botao" onclick="insert('7')">7</button></td>
                    <td><button class="botao" onclick="insert('8')">8</button></td>
                    <td><button class="botao" onclick="insert('9')">9</button></td>
                    <td><button class="botao" onclick="insert('-')">-</button></td>
                </tr>
                <tr>
                    <td><button class="botao" onclick="insert('4')">4</button></td>
                    <td><button class="botao" onclick="insert('5')">5</button></td>
                    <td><button class="botao" onclick="insert('6')">6</button></td>
                    <td><button class="botao" onclick="insert('+')">+</button></td>
                </tr>
                <tr>
                    <td><button class="botao" onclick="insert('1')">1</button></td>
                    <td><button class="botao" onclick="insert('2')">2</button></td>
                    <td><button class="botao" onclick="insert('3')">3</button></td>
                    <td rowspan="2"><button class="botao" style="height: 106px;" onclick="calcular()">=</button></td>
                </tr>
                <tr>
                    <td colspan="2"><button onclick="insert('0')" class="botao" style="width: 106px;">0</button></td>
                    <td><button class="botao" onclick="insert(',')">,</button></td>
                </tr>
            </table>
        
        </div>
    </div>
    <script>
        function insert(num){
           var numero = document.getElementById('resultado').innerHTML;
           document.getElementById('resultado').innerHTML = numero + num;
        }

        function clean(){
            document.getElementById('resultado').innerHTML = "";
        }
        function back(){
            var resultado = document.getElementById('resultado').innerHTML;
            document.getElementById('resultado').innerHTML = resultado.substring(0, resultado.length -1);
        }

        function calcular(){
            var resultado = document.getElementById('resultado').innerHTML;
            if(resultado){
                document.getElementById('resultado').innerHTML = eval(resultado);
            }
            else{
                document.getElementById('resultado').innerHTML = "Nada..."
            }
        }
    
    </script>
</body>
</html>
