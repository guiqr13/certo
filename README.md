<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rifa Beneficente - Tratamento de Diverticulite</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            min-height: 100vh;
            color: #333;
        }
        
        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 20px;
        }
        
        .header {
            background: white;
            border-radius: 15px;
            padding: 30px;
            text-align: center;
            margin-bottom: 30px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }
        
        .header h1 {
            color: #2c3e50;
            font-size: 2.5em;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.1);
        }
        
        .subtitle {
            color: #e74c3c;
            font-size: 1.3em;
            font-weight: bold;
            margin-bottom: 15px;
        }
        
        .causa {
            background: #f8f9fa;
            border-left: 5px solid #e74c3c;
            padding: 20px;
            margin: 20px 0;
            border-radius: 5px;
        }
        
        .info-box {
            background: white;
            border-radius: 15px;
            padding: 25px;
            margin-bottom: 20px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }
        
        .preco {
            font-size: 2em;
            color: #27ae60;
            font-weight: bold;
            text-align: center;
            margin: 20px 0;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.1);
        }
        
        .numeros-grid {
            display: grid;
            grid-template-columns: repeat(10, 1fr);
            gap: 5px;
            margin: 20px 0;
        }
        
        .numero {
            background: linear-gradient(45deg, #4CAF50, #45a049);
            color: white;
            padding: 10px;
            text-align: center;
            border-radius: 8px;
            font-weight: bold;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }
        
        .numero:hover {
            transform: translateY(-2px);
            box-shadow: 0 4px 10px rgba(0,0,0,0.2);
        }
        
        .numero.vendido {
            background: linear-gradient(45deg, #e74c3c, #c0392b);
            cursor: not-allowed;
        }
        
        .numero.selecionado {
            background: linear-gradient(45deg, #f39c12, #e67e22);
            transform: scale(1.1);
        }
        
        .controles {
            text-align: center;
            margin: 30px 0;
        }
        
        .btn {
            background: linear-gradient(45deg, #3498db, #2980b9);
            color: white;
            padding: 12px 25px;
            border: none;
            border-radius: 25px;
            font-size: 1.1em;
            cursor: pointer;
            margin: 5px;
            transition: all 0.3s ease;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        }
        
        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 15px rgba(0,0,0,0.2);
        }
        
        .btn-comprar {
            background: linear-gradient(45deg, #27ae60, #229954);
            font-size: 1.3em;
            padding: 15px 30px;
        }
        
        .contato {
            background: #34495e;
            color: white;
            border-radius: 15px;
            padding: 25px;
            text-align: center;
            margin-top: 30px;
        }
        
        .total-arrecadado {
            background: linear-gradient(45deg, #f39c12, #e67e22);
            color: white;
            padding: 15px;
            border-radius: 10px;
            text-align: center;
            margin: 20px 0;
            font-size: 1.2em;
            font-weight: bold;
        }
        
        .premio {
            background: linear-gradient(45deg, #9b59b6, #8e44ad);
            color: white;
            padding: 20px;
            border-radius: 15px;
            text-align: center;
            margin: 20px 0;
        }
        
        .premio h3 {
            font-size: 1.5em;
            margin-bottom: 10px;
        }
        
        @media (max-width: 600px) {
            .numeros-grid {
                grid-template-columns: repeat(5, 1fr);
            }
            
            .header h1 {
                font-size: 2em;
            }
            
            .preco {
                font-size: 1.5em;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="header">
            <h1>🎯 RIFA BENEFICENTE 🎯</h1>
            <div class="subtitle">Ajude no Tratamento de Diverticulite</div>
            <div class="causa">
                <strong>💙 NOSSA CAUSA:</strong><br>
                Arrecadação de fundos para custear exames necessários para o tratamento de diverticulite. 
                Sua contribuição fará a diferença na vida de quem precisa!
            </div>
        </div>
        
        <div class="info-box">
            <div class="preco">💰 R$ 10,00 por número</div>
            
            <div class="premio">
                <h3>🏆 PRÊMIO</h3>
                <p>🎂 1 kg de bolo + 🧁 100 docinhos</p>
            </div>
            
            <div class="total-arrecadado">
                📊 Meta: R$ 1.000,00 | Vendidos: <span id="vendidos">0</span>/100 números
                <br>Arrecadado: R$ <span id="arrecadado">0</span>
            </div>
            
            <h3 style="text-align: center; margin: 20px 0; color: #2c3e50;">
                🎲 Escolha seus números da sorte:
            </h3>
            
            <div class="numeros-grid" id="numerosGrid">
                <!-- Números serão gerados pelo JavaScript -->
            </div>
            
            <div class="controles">
                <button class="btn" onclick="limparSelecao()">🗑️ Limpar Seleção</button>
                <button class="btn" onclick="sortearNumeros()">🎲 Sortear 5 Números</button>
                <br><br>
                <div id="numerosEscolhidos" style="margin: 15px 0; font-weight: bold; color: #2c3e50;"></div>
                <div id="valorTotal" style="margin: 15px 0; font-size: 1.3em; color: #27ae60; font-weight: bold;"></div>
                <button class="btn btn-comprar" onclick="confirmarCompra()">
                    💳 Confirmar Compra
                </button>
            </div>
        </div>
        
        <div class="contato">
            <h3>📞 CONTATO PARA COMPRA</h3>
            <p><strong>WhatsApp:</strong> (64) 9 9292-4042</p>
            <p><strong>PIX:</strong> guiqr27@gmail.com</p>
            <p><strong>Responsável:</strong> Guilherme</p>
            <br>
            <p><strong>🎯 SORTEIO:</strong> 11/08/2024</p>
            <p><strong>📍 MODALIDADE:</strong> Ao vivo no Instagram @annarromodas</p>
            <p><strong>⏰ HORÁRIO:</strong> 20:00</p>
            <br>
            <p style="font-size: 0.9em; font-style: italic;">
                ✅ 100% do valor arrecadado será destinado ao tratamento<br>
                ✅ Prêmio doado pelos organizadores<br>
                ✅ Números só são reservados após confirmação do pagamento<br>
                ✅ Comprovantes de todas as transações serão disponibilizados
            </p>
        </div>
    </div>

    <script>
        let numerosSelecionados = [];
        let numerosVendidos = new Set(); // Inicia vazio - sem números pré-vendidos
        
        // Gerar grid de números
        function gerarNumeros() {
            const grid = document.getElementById('numerosGrid');
            grid.innerHTML = '';
            
            for (let i = 1; i <= 100; i++) {
                const numero = document.createElement('div');
                numero.className = 'numero';
                numero.textContent = i.toString().padStart(2, '0');
                numero.dataset.numero = i;
                
                if (numerosVendidos.has(i)) {
                    numero.classList.add('vendido');
                    numero.textContent += ' ❌';
                } else {
                    numero.addEventListener('click', () => toggleNumero(i, numero));
                }
                
                grid.appendChild(numero);
            }
        }
        
        function toggleNumero(numero, elemento) {
            if (numerosVendidos.has(numero)) return;
            
            const index = numerosSelecionados.indexOf(numero);
            if (index > -1) {
                numerosSelecionados.splice(index, 1);
                elemento.classList.remove('selecionado');
            } else {
                numerosSelecionados.push(numero);
                elemento.classList.add('selecionado');
            }
            
            atualizarInfo();
        }
        
        function atualizarInfo() {
            const numerosEscolhidos = document.getElementById('numerosEscolhidos');
            const valorTotal = document.getElementById('valorTotal');
            
            if (numerosSelecionados.length > 0) {
                numerosEscolhidos.textContent = `Números escolhidos: ${numerosSelecionados.sort((a, b) => a - b).join(', ')}`;
                valorTotal.textContent = `Valor total: R$ ${(numerosSelecionados.length * 10).toFixed(2)}`;
            } else {
                numerosEscolhidos.textContent = '';
                valorTotal.textContent = '';
            }
            
            // Atualizar contador
            document.getElementById('vendidos').textContent = numerosVendidos.size;
            document.getElementById('arrecadado').textContent = (numerosVendidos.size * 10).toFixed(2);
        }
        
        function limparSelecao() {
            numerosSelecionados = [];
            document.querySelectorAll('.numero.selecionado').forEach(num => {
                num.classList.remove('selecionado');
            });
            atualizarInfo();
        }
        
        function sortearNumeros() {
            limparSelecao();
            const disponiveis = [];
            for (let i = 1; i <= 100; i++) {
                if (!numerosVendidos.has(i)) {
                    disponiveis.push(i);
                }
            }
            
            if (disponiveis.length < 5) {
                alert('Não há números suficientes disponíveis para sortear!');
                return;
            }
            
            for (let i = 0; i < 5 && disponiveis.length > 0; i++) {
                const randomIndex = Math.floor(Math.random() * disponiveis.length);
                const numeroSorteado = disponiveis.splice(randomIndex, 1)[0];
                numerosSelecionados.push(numeroSorteado);
                
                const elemento = document.querySelector(`[data-numero="${numeroSorteado}"]`);
                elemento.classList.add('selecionado');
            }
            
            atualizarInfo();
        }
        
        function confirmarCompra() {
            if (numerosSelecionados.length === 0) {
                alert('⚠️ Selecione pelo menos um número!');
                return;
            }
            
            const valor = numerosSelecionados.length * 10;
            const numeros = numerosSelecionados.sort((a, b) => a - b).join(', ');
            
            const mensagem = `🎯 RIFA BENEFICENTE - Tratamento Diverticulite\n\n` +
                           `📋 Números escolhidos: ${numeros}\n` +
                           `💰 Valor total: R$ ${valor.toFixed(2)}\n\n` +
                           `Por favor, me confirme a reserva destes números!`;
            
            // Mostrar mensagem para contato
            alert(`🎯 NÚMEROS SELECIONADOS!\n\nNúmeros: ${numeros}\nValor: R$ ${valor.toFixed(2)}\n\n📱 PRÓXIMO PASSO:\nEntre em contato pelo WhatsApp (64) 9 9292-4042 com esta mensagem:\n\n"${mensagem}"\n\n⚠️ Os números só serão reservados após confirmação do pagamento!`);
            
            // Limpar seleção (números só são marcados como vendidos após confirmação pelo responsável)
            limparSelecao();
        }
        
        // Função para o responsável marcar números como vendidos (seria usada pelo admin)
        function marcarComoVendido(numerosArray) {
            numerosArray.forEach(num => {
                numerosVendidos.add(parseInt(num));
                salvarNumeroVendido(parseInt(num));
            });
            gerarNumeros();
            atualizarInfo();
        }
        
        // Função para administração (seria protegida por senha em sistema real)
        function adminPanel() {
            const senha = prompt('🔐 Digite a senha de administrador:');
            if (senha === 'admin123') { // Em sistema real, seria hash seguro
                const numerosVender = prompt('📝 Digite os números vendidos separados por vírgula (ex: 1,5,10):');
                if (numerosVender) {
                    const numerosArray = numerosVender.split(',').map(n => n.trim());
                    marcarComoVendido(numerosArray);
                    alert('✅ Números marcados como vendidos!');
                }
            } else if (senha !== null) {
                alert('❌ Senha incorreta!');
            }
        }
        
        // Adicionar duplo clique para acessar painel admin (escondido)
        document.addEventListener('dblclick', function(e) {
            if (e.ctrlKey) { // Ctrl + duplo clique
                adminPanel();
            }
        });
        
        // Sistema de persistência em memória
        function carregarNumerosVendidos() {
            // Inicia sempre vazio - todos os números disponíveis
            numerosVendidos = new Set();
        }
        
        function salvarNumeroVendido(numero) {
            // Em um sistema real, isso salvaria no banco de dados
            // Por enquanto, mantém apenas na sessão
            numerosVendidos.add(numero);
            localStorage.setItem('numerosVendidos', JSON.stringify([...numerosVendidos]));
        }
        
        function carregarDados() {
            // Sempre inicia com todos os números disponíveis
            numerosVendidos = new Set();
        }
        
        // Inicializar
        carregarDados();
        gerarNumeros();
        atualizarInfo();
    </script>
</body>
</html>
