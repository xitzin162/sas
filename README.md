-- Sistema de Keys
local validKeys = {
    "taf-pfmrsh-aim",
    "taf-atiwk7-aim",
    "taf-n82j7s-aim",
    "taf-lmlzcq-aim",
    "taf-khd6o2-aim",
    "taf-4kwq94-aim",
    "taf-c6d3dm-aim",
    "taf-0zwsax-aim",
    "taf-rc86is-aim",
    "taf-w2ixfu-aim",
    "taf-fbldbl-aim",
    "taf-ia01g0-aim",
    "taf-afhdbz-aim",
    "taf-mn301w-aim",
    "taf-0u7p9k-aim",
    "taf-09cvnj-aim",
    "taf-2ddl2h-aim",
    "taf-aq6uub-aim",
    "taf-9e5tzt-aim",
    "taf-wqrmed-aim",
    "taf-qhrj1u-aim",
    "taf-vk11qx-aim",
    "taf-sfbjvk-aim",
    "taf-j79g08-aim",
    "taf-vnt2qg-aim",
    "taf-8kldxs-aim",
    "taf-w14tjm-aim",
    "taf-62bmot-aim",
    "taf-9gdz52-aim",
    "taf-dqyxd3-aim",
    "taf-b358xg-aim",
    "taf-85y8qn-aim",
    "taf-xgo87v-aim",
    "taf-4eq3jm-aim",
    "taf-fkjciw-aim",
    "taf-kgwj9n-aim",
    "taf-4hrou2-aim",
    "taf-yksy50-aim",
    "taf-kdb9cs-aim",
    "taf-d80per-aim",
    "taf-l30fai-aim",
    "taf-lswliu-aim",
    "taf-ag7ius-aim",
    "taf-vst1yl-aim",
    "taf-wo8s8a-aim",
    "taf-npvznn-aim",
    "taf-5tdner-aim",
    "taf-qfci9j-aim",
    "taf-3bk53z-aim",
    "taf-f86jqs-aim",
    "taf-f6hgi7-aim",
    "taf-k4h33s-aim",
    "taf-2gy8qf-aim",
    "taf-x9tfg4-aim",
    "taf-3ytx6c-aim",
    "taf-u7d9wf-aim",
    "taf-lkcilu-aim",
    "taf-d6orqj-aim",
    "taf-y7ai6r-aim",
    "taf-xzqzto-aim",
    "taf-wzhxtx-aim",
    "taf-hdnyel-aim",
    "taf-zy2n7l-aim",
    "taf-72cjo8-aim",
    "taf-w4l0rp-aim",
    "taf-11r6pa-aim",
    "taf-84y498-aim",
    "taf-215o3y-aim",
    "taf-ly88qj-aim",
    "taf-cal2sa-aim",
    "taf-t1cs8e-aim",
    "taf-17yauv-aim",
    "taf-7fwesc-aim",
    "taf-uo0t1o-aim",
    "taf-eidk50-aim",
    "taf-0sr2nh-aim",
    "taf-zq1yj4-aim",
    "taf-66p2lx-aim",
    "taf-4hmbda-aim",
    "taf-342xv6-aim",
    "taf-qeroi1-aim",
    "taf-ch4cm8-aim",
    "taf-jq81q2-aim",
    "taf-0ksbw8-aim",
    "taf-zn5jgr-aim",
    "taf-icf1oh-aim",
    "taf-m5xib4-aim",
    "taf-f5hv70-aim",
    "taf-sml4ic-aim",
    "taf-q7k1jl-aim",
    "taf-95z6zt-aim",
    "taf-sjzvqx-aim",
    "taf-b7x6nb-aim",
    "taf-ov9rde-aim",
    "taf-smrlmv-aim",
    "taf-lio71w-aim",
    "taf-r5ietr-aim",
    "taf-y3252l-aim"
}

local keyValidated = false
local keyInterface = nil

-- Função para validar key
function validateKey(inputKey)
    for _, validKey in pairs(validKeys) do
        if inputKey == validKey then
            return true
        end
    end
    return false
end

-- Função para criar interface de key
function createKeyInterface()
    local keyScreenGui = Instance.new("ScreenGui")
    keyScreenGui.Name = "KeyInterface"
    keyScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
    keyScreenGui.ResetOnSpawn = false
    
    -- Frame principal
    local keyFrame = Instance.new("Frame")
    keyFrame.Size = UDim2.new(0, 300, 0, 200)
    keyFrame.Position = UDim2.new(0.5, -150, 0.5, -100)
    keyFrame.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
    keyFrame.BorderSizePixel = 0
    keyFrame.Parent = keyScreenGui
    
    local keyCorner = Instance.new("UICorner")
    keyCorner.CornerRadius = UDim.new(0, 8)
    keyCorner.Parent = keyFrame
    
    -- Título
    local keyTitle = Instance.new("TextLabel")
    keyTitle.Size = UDim2.new(1, 0, 0, 40)
    keyTitle.Position = UDim2.new(0, 0, 0, 0)
    keyTitle.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
    keyTitle.BackgroundTransparency = 0.3
    keyTitle.Text = "🔐 AUTENTICAÇÃO NECESSÁRIA"
    keyTitle.TextColor3 = Color3.fromRGB(255, 255, 255)
    keyTitle.Font = Enum.Font.GothamBold
    keyTitle.TextSize = 16
    keyTitle.Parent = keyFrame
    
    -- Texto de instrução
    local keyInstruction = Instance.new("TextLabel")
    keyInstruction.Size = UDim2.new(1, -20, 0, 30)
    keyInstruction.Position = UDim2.new(0, 10, 0, 50)
    keyInstruction.BackgroundTransparency = 1
    keyInstruction.Text = "Digite sua key"
    keyInstruction.TextColor3 = Color3.fromRGB(200, 200, 200)
    keyInstruction.Font = Enum.Font.Gotham
    keyInstruction.TextSize = 12
    keyInstruction.TextWrapped = true
    keyInstruction.Parent = keyFrame
    
    -- Campo de entrada da key
    local keyInput = Instance.new("TextBox")
    keyInput.Size = UDim2.new(1, -40, 0, 35)
    keyInput.Position = UDim2.new(0, 20, 0, 90)
    keyInput.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
    keyInput.BorderSizePixel = 0
    keyInput.Text = ""
    keyInput.PlaceholderText = "Insira sua key aqui..."
    keyInput.TextColor3 = Color3.fromRGB(255, 255, 255)
    keyInput.PlaceholderColor3 = Color3.fromRGB(150, 150, 150)
    keyInput.Font = Enum.Font.Gotham
    keyInput.TextSize = 14
    keyInput.Parent = keyFrame
    
    local inputCorner = Instance.new("UICorner")
    inputCorner.CornerRadius = UDim.new(0, 4)
    inputCorner.Parent = keyInput
    
    -- Botão de validação
    local validateButton = Instance.new("TextButton")
    validateButton.Size = UDim2.new(0, 100, 0, 30)
    validateButton.Position = UDim2.new(0.5, -50, 0, 140)
    validateButton.BackgroundColor3 = Color3.fromRGB(0, 120, 200)
    validateButton.BorderSizePixel = 0
    validateButton.Text = "VALIDAR"
    validateButton.TextColor3 = Color3.fromRGB(255, 255, 255)
    validateButton.Font = Enum.Font.GothamBold
    validateButton.TextSize = 12
    validateButton.Parent = keyFrame
    
    local buttonCorner = Instance.new("UICorner")
    buttonCorner.CornerRadius = UDim.new(0, 4)
    buttonCorner.Parent = validateButton
    
    -- Status da validação
    local keyStatus = Instance.new("TextLabel")
    keyStatus.Size = UDim2.new(1, -20, 0, 20)
    keyStatus.Position = UDim2.new(0, 10, 0, 175)
    keyStatus.BackgroundTransparency = 1
    keyStatus.Text = ""
    keyStatus.TextColor3 = Color3.fromRGB(255, 100, 100)
    keyStatus.Font = Enum.Font.Gotham
    keyStatus.TextSize = 11
    keyStatus.Parent = keyFrame
    
    -- Função de validação
    local function attemptValidation()
        local inputText = keyInput.Text
        
        if inputText == "" then
            keyStatus.Text = "❌ Digite uma key"
            keyStatus.TextColor3 = Color3.fromRGB(255, 100, 100)
            return
        end
        
        if validateKey(inputText) then
            keyStatus.Text = "✅ Key válida! Carregando..."
            keyStatus.TextColor3 = Color3.fromRGB(100, 255, 100)
            
            wait(1)
            keyValidated = true
            keyScreenGui:Destroy()
            initializeMainScript()
        else
            keyStatus.Text = "❌ Key inválida"
            keyStatus.TextColor3 = Color3.fromRGB(255, 100, 100)
            keyInput.Text = ""
        end
    end
    
    -- Eventos do botão e enter
    validateButton.MouseButton1Click:Connect(attemptValidation)
    keyInput.FocusLost:Connect(function(enterPressed)
        if enterPressed then
            attemptValidation()
        end
    end)
    
    keyInterface = keyScreenGui
end

-- Função para inicializar o script principal após validação
function initializeMainScript()
    -- Configurações
    local aimlockKey = "e"
    local espKey = "f"
    local triggerbotKey = "v"
    local walkspeedKey = "g"
    local flyKey = "c"
    local aimlockEnabled = false
    local espEnabled = false
    local triggerbotEnabled = false
    local walkspeedEnabled = false
    local flyEnabled = false

    -- Variáveis
    local players = game:GetService("Players")
    local localPlayer = players.LocalPlayer
    local mouse = localPlayer:GetMouse()
    local camera = workspace.CurrentCamera
    local runService = game:GetService("RunService")
    local userInputService = game:GetService("UserInputService")
    local contextActionService = game:GetService("ContextActionService")

    -- Tabela para armazenar dados do ESP
    local espData = {}

    -- Configurações do TriggerBot
    local triggerbotDelay = 0.02  -- Delay entre os disparos (segundos)
    local triggerbotRange = 100     -- Alcance máximo do TriggerBot (studs)
    local lastTriggerTime = 0     -- Último momento em que o TriggerBot disparou

    -- Configurações do WalkSpeed
    local normalWalkspeed = 16    -- Velocidade normal de movimento
    local boostedWalkspeed =60   -- Velocidade aumentada
    local currentWalkspeed = normalWalkspeed

    -- Configurações do Fly
    local flySpeed = 50           -- Velocidade do voo
    local flyBoostMultiplier = 2  -- Multiplicador de velocidade quando shift está pressionado
    local bodyVelocity = nil       -- Instância do BodyVelocity para voar
    local bodyGyro = nil           -- Instância do BodyGyro para estabilizar

    -- Criar interface
    local screenGui = Instance.new("ScreenGui")
    screenGui.Name = "AimlockInterface"
    screenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
    screenGui.ResetOnSpawn = false

    local mainFrame = Instance.new("Frame")
    mainFrame.Size = UDim2.new(0, 180, 0, 160)
    mainFrame.Position = UDim2.new(0, 10, 0, 10)
    mainFrame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
    mainFrame.BorderSizePixel = 0
    mainFrame.BackgroundTransparency = 0.4
    mainFrame.Parent = screenGui

    local corner = Instance.new("UICorner")
    corner.CornerRadius = UDim.new(0, 6)
    corner.Parent = mainFrame

    local title = Instance.new("TextLabel")
    title.Size = UDim2.new(1, 0, 0, 25)
    title.Position = UDim2.new(0, 0, 0, 0)
    title.BackgroundColor3 = Color3.fromRGB(20, 20, 20)
    title.BackgroundTransparency = 0.5
    title.Text = "Aimlock & ESP & Trigger"
    title.TextColor3 = Color3.fromRGB(255, 255, 255)
    title.Font = Enum.Font.GothamBold
    title.TextSize = 14
    title.Parent = mainFrame

    local aimlockStatus = Instance.new("TextLabel")
    aimlockStatus.Size = UDim2.new(1, -10, 0, 20)
    aimlockStatus.Position = UDim2.new(0, 5, 0, 30)
    aimlockStatus.BackgroundTransparency = 1
    aimlockStatus.Text = "Aimlock: DESATIVADO [E]"
    aimlockStatus.TextColor3 = Color3.fromRGB(255, 100, 100)
    aimlockStatus.Font = Enum.Font.Gotham
    aimlockStatus.TextSize = 12
    aimlockStatus.TextXAlignment = Enum.TextXAlignment.Left
    aimlockStatus.Parent = mainFrame

    local espStatus = Instance.new("TextLabel")
    espStatus.Size = UDim2.new(1, -10, 0, 20)
    espStatus.Position = UDim2.new(0, 5, 0, 55)
    espStatus.BackgroundTransparency = 1
    espStatus.Text = "ESP: DESATIVADO [F]"
    espStatus.TextColor3 = Color3.fromRGB(255, 100, 100)
    espStatus.Font = Enum.Font.Gotham
    espStatus.TextSize = 12
    espStatus.TextXAlignment = Enum.TextXAlignment.Left
    espStatus.Parent = mainFrame

    local triggerbotStatus = Instance.new("TextLabel")
    triggerbotStatus.Size = UDim2.new(1, -10, 0, 20)
    triggerbotStatus.Position = UDim2.new(0, 5, 0, 80)
    triggerbotStatus.BackgroundTransparency = 1
    triggerbotStatus.Text = "TriggerBot: DESATIVADO [V]"
    triggerbotStatus.TextColor3 = Color3.fromRGB(255, 100, 100)
    triggerbotStatus.Font = Enum.Font.Gotham
    triggerbotStatus.TextSize = 12
    triggerbotStatus.TextXAlignment = Enum.TextXAlignment.Left
    triggerbotStatus.Parent = mainFrame

    local walkspeedStatus = Instance.new("TextLabel")
    walkspeedStatus.Size = UDim2.new(1, -10, 0, 20)
    walkspeedStatus.Position = UDim2.new(0, 5, 0, 105)
    walkspeedStatus.BackgroundTransparency = 1
    walkspeedStatus.Text = "WalkSpeed: NORMAL [G]"
    walkspeedStatus.TextColor3 = Color3.fromRGB(255, 100, 100)
    walkspeedStatus.Font = Enum.Font.Gotham
    walkspeedStatus.TextSize = 12
    walkspeedStatus.TextXAlignment = Enum.TextXAlignment.Left
    walkspeedStatus.Parent = mainFrame

    local flyStatus = Instance.new("TextLabel")
    flyStatus.Size = UDim2.new(1, -10, 0, 20)
    flyStatus.Position = UDim2.new(0, 5, 0, 130)
    flyStatus.BackgroundTransparency = 1
    flyStatus.Text = "Fly: DESATIVADO [C]"
    flyStatus.TextColor3 = Color3.fromRGB(255, 100, 100)
    flyStatus.Font = Enum.Font.Gotham
    flyStatus.TextSize = 12
    flyStatus.TextXAlignment = Enum.TextXAlignment.Left
    flyStatus.Parent = mainFrame

    local infoText = Instance.new("TextLabel")
    infoText.Size = UDim2.new(1, -10, 0, 20)
    infoText.Position = UDim2.new(0, 5, 0, 150)
    infoText.BackgroundTransparency = 1
    infoText.Text = "Modo Educativo"
    infoText.TextColor3 = Color3.fromRGB(150, 150, 150)
    infoText.Font = Enum.Font.Gotham
    infoText.TextSize = 10
    infoText.TextXAlignment = Enum.TextXAlignment.Left
    infoText.Parent = mainFrame

    -- Função para atualizar a interface
    function updateInterface()
        aimlockStatus.Text = "Aimlock: " .. (aimlockEnabled and "ATIVADO [E]" or "DESATIVADO [E]")
        aimlockStatus.TextColor3 = aimlockEnabled and Color3.fromRGB(100, 255, 100) or Color3.fromRGB(255, 100, 100)
        
        espStatus.Text = "ESP: " .. (espEnabled and "ATIVADO [F]" or "DESATIVADO [F]")
        espStatus.TextColor3 = espEnabled and Color3.fromRGB(100, 255, 100) or Color3.fromRGB(255, 100, 100)
        
        triggerbotStatus.Text = "TriggerBot: " .. (triggerbotEnabled and "ATIVADO [V]" or "DESATIVADO [V]")
        triggerbotStatus.TextColor3 = triggerbotEnabled and Color3.fromRGB(100, 255, 100) or Color3.fromRGB(255, 100, 100)
        
        walkspeedStatus.Text = "WalkSpeed: " .. (walkspeedEnabled and "BOOST ["..boostedWalkspeed.."] [G]" or "NORMAL ["..normalWalkspeed.."] [G]")
        walkspeedStatus.TextColor3 = walkspeedEnabled and Color3.fromRGB(100, 255, 100) or Color3.fromRGB(255, 100, 100)
        
        flyStatus.Text = "Fly: " .. (flyEnabled and "ATIVADO [C]" or "DESATIVADO [C]")
        flyStatus.TextColor3 = flyEnabled and Color3.fromRGB(100, 255, 100) or Color3.fromRGB(255, 100, 100)
    end

    -- Função para atualizar a velocidade de movimento
    function updateWalkspeed()
        if localPlayer.Character and localPlayer.Character:FindFirstChild("Humanoid") then
            localPlayer.Character.Humanoid.WalkSpeed = currentWalkspeed
        end
    end

    -- Função para alternar a velocidade de movimento
    function toggleWalkspeed()
        walkspeedEnabled = not walkspeedEnabled
        
        if walkspeedEnabled then
            currentWalkspeed = boostedWalkspeed
            print("WalkSpeed aumentado para " .. boostedWalkspeed)
        else
            currentWalkspeed = normalWalkspeed
            print("WalkSpeed normalizado para " .. normalWalkspeed)
        end
        
        updateWalkspeed()
        updateInterface()
    end

    -- Função para ativar/desativar o fly
    function toggleFly()
        flyEnabled = not flyEnabled
        
        if flyEnabled then
            startFly()
            print("Fly ativado")
        else
            stopFly()
            print("Fly desativado")
        end
        
        updateInterface()
    end

    -- Função para iniciar o fly
    function startFly()
        if not localPlayer.Character or not localPlayer.Character:FindFirstChild("HumanoidRootPart") then
            return
        end
        
        local humanoidRootPart = localPlayer.Character.HumanoidRootPart
        
        -- Criar BodyVelocity para movimento
        bodyVelocity = Instance.new("BodyVelocity")
        bodyVelocity.Velocity = Vector3.new(0, 0, 0)
        bodyVelocity.MaxForce = Vector3.new(10000, 10000, 10000)
        bodyVelocity.P = 1000
        bodyVelocity.Parent = humanoidRootPart
        
        -- Criar BodyGyro para estabilização
        bodyGyro = Instance.new("BodyGyro")
        bodyGyro.MaxTorque = Vector3.new(10000, 10000, 10000)
        bodyGyro.P = 1000
        bodyGyro.D = 50
        bodyGyro.Parent = humanoidRootPart
        
        -- Configurar gyro para manter a rotação atual
        bodyGyro.CFrame = humanoidRootPart.CFrame
        
        -- Desativar gravidade no humanoide
        if localPlayer.Character:FindFirstChild("Humanoid") then
            localPlayer.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.FallingDown, false)
            localPlayer.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Ragdoll, false)
            localPlayer.Character.Humanoid:ChangeState(Enum.HumanoidStateType.Flying)
        end
    end

    -- Função para parar o fly
    function stopFly()
        if bodyVelocity then
            bodyVelocity:Destroy()
            bodyVelocity = nil
        end
        
        if bodyGyro then
            bodyGyro:Destroy()
            bodyGyro = nil
        end
        
        -- Reativar gravidade no humanoide
        if localPlayer.Character and localPlayer.Character:FindFirstChild("Humanoid") then
            localPlayer.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.FallingDown, true)
            localPlayer.Character.Humanoid:SetStateEnabled(Enum.HumanoidStateType.Ragdoll, true)
            localPlayer.Character.Humanoid:ChangeState(Enum.HumanoidStateType.Landed)
        end
    end

    -- Função para controlar o fly
    function controlFly()
        if not flyEnabled or not bodyVelocity or not bodyGyro or not localPlayer.Character or not localPlayer.Character:FindFirstChild("HumanoidRootPart") then
            return
        end
        
        local humanoidRootPart = localPlayer.Character.HumanoidRootPart
        
        -- Calcular direção do movimento baseado nas teclas pressionadas
        local direction = Vector3.new(0, 0, 0)
        
        if userInputService:IsKeyDown(Enum.KeyCode.W) then
            direction = direction + camera.CFrame.LookVector
        end
        
        if userInputService:IsKeyDown(Enum.KeyCode.S) then
            direction = direction - camera.CFrame.LookVector
        end
        
        if userInputService:IsKeyDown(Enum.KeyCode.A) then
            direction = direction - camera.CFrame.RightVector
        end
        
        if userInputService:IsKeyDown(Enum.KeyCode.D) then
            direction = direction + camera.CFrame.RightVector
        end
        
        if userInputService:IsKeyDown(Enum.KeyCode.Space) then
            direction = direction + Vector3.new(0, 1, 0)
        end
        
        if userInputService:IsKeyDown(Enum.KeyCode.LeftControl) or userInputService:IsKeyDown(Enum.KeyCode.C) then
            direction = direction - Vector3.new(0, 1, 0)
        end
        
        -- Normalizar direção e aplicar velocidade
        if direction.Magnitude > 0 then
            direction = direction.Unit
            
            -- Aplicar boost se shift estiver pressionado
            local currentSpeed = flySpeed
            if userInputService:IsKeyDown(Enum.KeyCode.LeftShift) then
                currentSpeed = flySpeed * flyBoostMultiplier
            end
            
            bodyVelocity.Velocity = direction * currentSpeed
        else
            bodyVelocity.Velocity = Vector3.new(0, 0, 0)
        end
        
        -- Atualizar gyro para manter a rotação da câmera
        bodyGyro.CFrame = CFrame.new(humanoidRootPart.Position, humanoidRootPart.Position + camera.CFrame.LookVector)
    end

    -- Função para encontrar o jogador mais próximo do cursor
    function findClosestPlayer()
        local closestPlayer = nil
        local shortestDistance = math.huge
        
        for _, player in pairs(players:GetPlayers()) do
            if player ~= localPlayer and player.Character and player.Character:FindFirstChild("HumanoidRootPart") and player.Character:FindFirstChild("Humanoid") and player.Character.Humanoid.Health > 0 then
                local character = player.Character
                local humanoidRootPart = character.HumanoidRootPart
                
                -- Verificar se o jogador está visível na tela
                local position, onScreen = camera:WorldToViewportPoint(humanoidRootPart.Position)
                
                if onScreen then
                    -- Calcular distância do cursor para o jogador
                    local mouseDistance = (Vector2.new(position.X, position.Y) - Vector2.new(mouse.X, mouse.Y)).Magnitude
                    
                    if mouseDistance < shortestDistance then
                        shortestDistance = mouseDistance
                        closestPlayer = player
                    end
                end
            end
        end
        
        return closestPlayer
    end

    -- Função melhorada para verificar se o mouse está sobre um jogador (para o TriggerBot)
    function isMouseOverPlayer()
        local ray = camera:ViewportPointToRay(mouse.X, mouse.Y)
        local direction = ray.Direction.Unit * triggerbotRange
        
        local params = RaycastParams.new()
        params.FilterType = Enum.RaycastFilterType.Blacklist
        params.FilterDescendantsInstances = {localPlayer.Character, camera}
        
        local result = workspace:Raycast(ray.Origin, direction, params)
        
        if result and result.Instance then
            -- Encontrar o jogador dono da parte atingida
            local character = result.Instance:FindFirstAncestorOfClass("Model")
            if character and players:GetPlayerFromCharacter(character) and players:GetPlayerFromCharacter(character) ~= localPlayer then
                local humanoid = character:FindFirstChild("Humanoid")
                if humanoid and humanoid.Health > 0 then
                    return true
                end
            end
        end
        
        return false
    end

    -- Função para simular um clique do mouse (melhorada)
    function simulateMouseClick()
        -- Método 1: Usando virtual input (mais confiável)
        local virtualInput = game:GetService("VirtualInputManager")
        
        -- Simular pressionar o botão
        virtualInput:SendMouseButtonEvent(mouse.X, mouse.Y, 0, true, game, 1)
        
        -- Pequeno delay para simular um clique real
        task.wait(0.05)
        
        -- Simular soltar o botão
        virtualInput:SendMouseButtonEvent(mouse.X, mouse.Y, 0, false, game, 1)
        
        -- Método alternativo: Usar o contexto de ação se disponível
        pcall(function()
            contextActionService:CallFunction("Fire", Enum.UserInputState.Begin)
            task.wait(0.05)
            contextActionService:CallFunction("Fire", Enum.UserInputState.End)
        end)
    end

    -- Função para criar ESP
    function createESP(player)
        if not player.Character then return end
        
        local character = player.Character
        local humanoidRootPart = character:FindFirstChild("HumanoidRootPart")
        if not humanoidRootPart then return end
        
        -- Criar caixa de ESP
        local espBox = Drawing.new("Square")
        espBox.Visible = false
        espBox.Color = Color3.fromRGB(255, 0, 0)
        espBox.Thickness = 2
        espBox.Filled = false
        
        -- Criar texto com nome do jogador
        local espText = Drawing.new("Text")
        espText.Visible = false
        espText.Color = Color3.fromRGB(255, 255, 255)
        espText.Size = 16
        espText.Center = true
        espText.Outline = true
        
        -- Criar linha de saúde
        local healthBar = Drawing.new("Line")
        healthBar.Visible = false
        healthBar.Color = Color3.fromRGB(0, 255, 0)
        healthBar.Thickness = 2
        
        -- Armazenar dados do ESP na nossa tabela
        espData[player] = {
            box = espBox,
            text = espText,
            healthBar = healthBar,
            connection = nil
        }
        
        -- Conexão para atualizar o ESP
        espData[player].connection = runService.RenderStepped:Connect(function()
            if not player or not player.Character or not humanoidRootPart or not humanoidRootPart.Parent then
                if espData[player] then
                    if espData[player].box then espData[player].box:Remove() end
                    if espData[player].text then espData[player].text:Remove() end
                    if espData[player].healthBar then espData[player].healthBar:Remove() end
                    if espData[player].connection then espData[player].connection:Disconnect() end
                    espData[player] = nil
                end
                return
            end
            
            local humanoid = player.Character:FindFirstChild("Humanoid")
            if not humanoid then return end
            
            local position, onScreen = camera:WorldToViewportPoint(humanoidRootPart.Position)
            
            if onScreen and espEnabled then
                -- Calcular tamanho da caixa baseado na distância
                local distance = (camera.CFrame.Position - humanoidRootPart.Position).Magnitude
                local scale = 1000 / distance
                
                -- Atualizar caixa ESP
                espBox.Size = Vector2.new(scale, scale * 2)
                espBox.Position = Vector2.new(position.X - espBox.Size.X / 2, position.Y - espBox.Size.Y / 2)
                espBox.Visible = true
                
                -- Atualizar texto ESP
                espText.Text = player.Name .. " [" .. math.floor(distance) .. " studs]"
                espText.Position = Vector2.new(position.X, position.Y - espBox.Size.Y / 2 - 20)
                espText.Visible = true
                
                -- Atualizar barra de saúde
                local healthPercent = humanoid.Health / humanoid.MaxHealth
                healthBar.From = Vector2.new(position.X - scale/2, position.Y + scale + 5)
                healthBar.To = Vector2.new(position.X - scale/2 + scale * healthPercent, position.Y + scale + 5)
                healthBar.Visible = true
                
                -- Mudar cor da barra de saúde baseado na saúde
                if healthPercent > 0.5 then
                    healthBar.Color = Color3.fromRGB(0, 255, 0)  -- Verde
                elseif healthPercent > 0.25 then
                    healthBar.Color = Color3.fromRGB(255, 255, 0)  -- Amarelo
                else
                    healthBar.Color = Color3.fromRGB(255, 0, 0)  -- Vermelho
                end
            else
                espBox.Visible = false
                espText.Visible = false
                healthBar.Visible = false
            end
        end)
    end

    -- Ativar/desativar ESP para todos os jogadores
    function toggleESP(enable)
        espEnabled = enable
        
        for _, player in pairs(players:GetPlayers()) do
            if player ~= localPlayer then
                if enable then
                    if not player.Character then
                        player.CharacterAdded:Wait()
                    end
                    createESP(player)
                else
                    if espData[player] then
                        if espData[player].box then espData[player].box:Remove() end
                        if espData[player].text then espData[player].text:Remove() end
                        if espData[player].healthBar then espData[player].healthBar:Remove() end
                        if espData[player].connection then espData[player].connection:Disconnect() end
                        espData[player] = nil
                    end
                end
            end
        end
        updateInterface()
    end

    -- Configurar ESP para novos jogadores
    players.PlayerAdded:Connect(function(player)
        if espEnabled then
            player.CharacterAdded:Connect(function(character)
                wait(1) -- Esperar o personagem carregar completamente
                createESP(player)
            end)
        end
    end)

    -- Limpar ESP quando um jogador sai
    players.PlayerRemoving:Connect(function(player)
        if espData[player] then
            if espData[player].box then espData[player].box:Remove() end
            if espData[player].text then espData[player].text:Remove() end
            if espData[player].healthBar then espData[player].healthBar:Remove() end
            if espData[player].connection then espData[player].connection:Disconnect() end
            espData[player] = nil
        end
    end)

    -- Loop principal
    runService.RenderStepped:Connect(function()
        -- Aimlock
        if aimlockEnabled then
            local target = findClosestPlayer()
            
            if target and target.Character and target.Character:FindFirstChild("HumanoidRootPart") then
                local targetRoot = target.Character.HumanoidRootPart
                camera.CFrame = CFrame.new(camera.CFrame.Position, targetRoot.Position)
            end
        end
        
        -- TriggerBot: Atirar automaticamente quando o mouse estiver sobre um jogador
        if triggerbotEnabled then
            local currentTime = tick()
            if currentTime - lastTriggerTime >= triggerbotDelay then
                if isMouseOverPlayer() then
                    simulateMouseClick()
                    lastTriggerTime = currentTime
                end
            end
        end
        
        -- Atualizar WalkSpeed se necessário
        if localPlayer.Character and localPlayer.Character:FindFirstChild("Humanoid") then
            if localPlayer.Character.Humanoid.WalkSpeed ~= currentWalkspeed then
                updateWalkspeed()
            end
        end
        
        -- Controlar Fly
        controlFly()
    end)

    -- Configurar hotkeys
    userInputService.InputBegan:Connect(function(input, gameProcessed)
        if gameProcessed then return end
        
        if input.KeyCode == Enum.KeyCode[aimlockKey:upper()] then
            aimlockEnabled = not aimlockEnabled
            print("Aimlock " .. (aimlockEnabled and "ativado" or "desativado"))
            updateInterface()
        elseif input.KeyCode == Enum.KeyCode[espKey:upper()] then
            espEnabled = not espEnabled
            toggleESP(espEnabled)
            print("ESP " .. (espEnabled and "ativado" or "desativado"))
        elseif input.KeyCode == Enum.KeyCode[triggerbotKey:upper()] then
            triggerbotEnabled = not triggerbotEnabled
            print("TriggerBot " .. (triggerbotEnabled and "ativado" or "desativado"))
            updateInterface()
        elseif input.KeyCode == Enum.KeyCode[walkspeedKey:upper()] then
            toggleWalkspeed()
        elseif input.KeyCode == Enum.KeyCode[flyKey:upper()] then
            toggleFly()
        end
    end)

    -- Tornar a interface arrastável
    local dragging
    local dragInput
    local dragStart
    local startPos

    local function update(input)
        local delta = input.Position - dragStart
        mainFrame.Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y)
    end

    mainFrame.InputBegan:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.MouseButton1 then
            dragging = true
            dragStart = input.Position
            startPos = mainFrame.Position
            
            input.Changed:Connect(function()
                if input.UserInputState == Enum.UserInputState.End then
                    dragging = false
                end
            end)
        end
    end)

    mainFrame.InputChanged:Connect(function(input)
        if input.UserInputType == Enum.UserInputType.MouseMovement then
            dragInput = input
        end
    end)

    userInputService.InputChanged:Connect(function(input)
        if input == dragInput and dragging then
            update(input)
        end
    end)

    -- Atualizar WalkSpeed quando o personagem spawnar
    localPlayer.CharacterAdded:Connect(function(character)
        wait(1) -- Esperar o personagem carregar completamente
        updateWalkspeed()
        
        -- Se fly estava ativado, reativar
        if flyEnabled then
            stopFly()
            startFly()
        end
    end)

    -- Limpar fly quando o script for encerrado
    game:GetService("Players").PlayerRemoving:Connect(function(player)
        if player == localPlayer then
            stopFly()
        end
    end)

    -- Inicializar interface e WalkSpeed
    if localPlayer.Character then
        updateWalkspeed()
    end
    updateInterface()

    print("✅ Script carregado com sucesso!")
    print("Pressione " .. aimlockKey:upper() .. " para ativar/desativar o Aimlock")
    print("Pressione " .. espKey:upper() .. " para ativar/desativar o ESP")
    print("Pressione " .. triggerbotKey:upper() .. " para ativar/desativar o TriggerBot")
    print("Pressione " .. walkspeedKey:upper() .. " para aumentar/diminuir a WalkSpeed")
    print("Pressione " .. flyKey:upper() .. " para ativar/desativar o Fly")
    print("Controles do Fly: WASD (movimento), Espaço (subir), Ctrl (descer), Shift (boost)")
    print("Alcance do TriggerBot: " .. triggerbotRange .. " studs")
end

-- Função para gerar key aleatória (para teste)
function generateRandomKey()
    local letters = "abcdefghijklmnopqrstuvwxyz"
    local numbers = "0123456789"
    local chars = letters .. numbers
    
    local randomPart = ""
    for i = 1, 6 do
        local randomIndex = math.random(1, #chars)
        randomPart = randomPart .. chars:sub(randomIndex, randomIndex)
    end
    
    return "taf-" .. randomPart .. "-aim"
end

-- Inicializar sistema
print("🔐 Sistema de autenticação iniciado")
print("📋 Keys válidas disponíveis:")
for i, key in pairs(validKeys) do
    print("   " .. i .. ". " .. key)
end
print("🎲 Key aleatória gerada para teste: " .. generateRandomKey())

-- Criar interface de key
createKeyInterface()
