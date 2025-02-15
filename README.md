-- Importando a biblioteca GUI (substitua pela biblioteca específica do Delta GUI se necessário)
local gui = require("gui") -- Certifique-se de usar uma biblioteca GUI apropriada para Lua

-- Cria a janela principal para dispositivos móveis
local window = gui.createWindow("SONIC", 400, 300)

-- Define a posição da janela no centro da tela
window:setPosition(display.contentCenterX - window.width / 2, display.contentCenterY - window.height / 2)

-- Cria o botão de minimizar em forma de quadrado
local minimizeButton = gui.createButton("▢", 370, 10, 20, 20)

-- Função para minimizar a janela
minimizeButton.onClick = function()
    window:setVisible(false)
end

-- Adiciona o botão de minimizar à janela
window:addComponent(minimizeButton)

-- Cria o rótulo com a descrição e o link para o Discord
local discordLabel = gui.createLabel("Entre no nosso Discord: https://discord.gg/HsQUdUna", 10, 250, 380, 20)
window:addComponent(discordLabel)

-- Cria o botão "Passa sensi"
local sensiButton = gui.createButton("Passa sensi", display.contentCenterX - 50, display.contentCenterY - 20, 100, 40)

-- Função para exibir o campo numérico quando o botão é pressionado
sensiButton.onClick = function()
    numberField:setVisible(true)
end
window:addComponent(sensiButton)

-- Cria o campo numérico
local numberField = gui.createNumericField({
    value = 5,
    min = 0,
    max = 10,
    x = display.contentCenterX - 50,
    y = display.contentCenterY + 40,
    width = 100,
    height = 40,
    onChange = function(value)
        if value > 5 then
            -- Aumenta a lentidão da tela
            setGameSpeed("slow")
        else
            -- Deixa a tela mais fluida
            setGameSpeed("fast")
        end
    end
})
numberField:setVisible(false) -- Inicialmente invisível
window:addComponent(numberField)

-- Função para configurar a velocidade do jogo
function setGameSpeed(speed)
    if speed == "slow" then
        -- Ajuste o código aqui para aumentar a lentidão do jogo
    elseif speed == "fast" then
        -- Ajuste o código aqui para deixar a tela mais fluida
    end
end

-- Mostra a janela
window:show()

-- Função principal para configurar a interface gráfica
local function setupGUI()
    window:show()
end

-- Inicializa a configuração da interface gráfica
setupGUI()
