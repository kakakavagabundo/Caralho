-- ServerScriptService > LoopKillNPCs
local KILL_DELAY = 2  -- segundos entre cada "varredura" de NPCs

while true do
    task.wait(KILL_DELAY)

    for _, obj in pairs(workspace:GetDescendants()) do
        if obj:IsA("Humanoid") then
            local char = obj.Parent
            local player = game.Players:GetPlayerFromCharacter(char)
            if not player and obj.Health > 0 then
                obj.Health = 0
            end
        end
    end
end
