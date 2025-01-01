-- Função para detectar e exibir o nível atual do jogador
function showLevel()
    local player = game.Players.LocalPlayer
    local level = player.Data.Level.Value
    print("Seu nível atual é: " .. level)
end

-- Função para verificar se o jogador está perto de uma fruta
function checkForFruit()
    local player = game.Players.LocalPlayer
    local character = player.Character
    local fruit = workspace:FindFirstChild("Fruit") -- Substitua pelo nome da fruta se necessário
    if fruit and (fruit.Position - character.HumanoidRootPart.Position).Magnitude < 20 then
        print("Você está perto de uma fruta!")
    else
        print("Nenhuma fruta perto de você.")
    end
end

-- Função para coletar uma fruta (simulação de interação com o jogo)
function collectFruit()
    local player = game.Players.LocalPlayer
    local character = player.Character
    local fruit = workspace:FindFirstChild("Fruit") -- Substitua pelo nome da fruta se necessário
    if fruit and (fruit.Position - character.HumanoidRootPart.Position).Magnitude < 20 then
        print("Você pegou a fruta!")
        -- Aqui você pode adicionar lógica para pegar a fruta, por exemplo, ativando animações ou incrementando um contador.
    else
        print("Não há frutas perto.")
    end
end

-- Função para mostrar a quantidade de dinheiro do jogador
function showMoney()
    local player = game.Players.LocalPlayer
    local money = player.Data.Money.Value
    print("Seu saldo atual é: " .. money .. " Beli")
end

-- Função principal que será executada
function main()
    -- Exibe o nível do jogador
    showLevel()

    -- Verifica se o jogador está perto de uma fruta
    checkForFruit()

    -- Exibe o saldo de dinheiro do jogador
    showMoney()
end

-- Executa a função principal a cada 5 segundos
while true do
    wait(5)
    main()
end
