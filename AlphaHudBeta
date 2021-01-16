local toHide = {
["DarkRP_HUD"] = true,
["DarkRP_Hungermod"] = true,
["DarkRP_LocalPlayerHUD"] = true,
["DarkRP_EntityDisplay"] = false,
["DarkRP_Agenda"] = true,
["DarkRP_LockdownHUD"] = true,
["DarkRP_ArrestHud"] = true,
["CHudHealth"] = true,
["CHudBattery"] = true,
["CHudAmmo"] = true,
["CHudSecondary"] = true,
["CHudPoisonDamageIndicator"] = true,
["CHudSquadStatus"] = true,
}
hook.Add("HudShouldDraw", "HideHUD",
function ( name )
       if toHide[name] then return false end
end )

-- Локальные Переменные --

local x = 15
local y = ScrH() - 150

-- Шрифты --

-- ХП --
surface.CreateFont('health', {
    font = 'Open Sans Bold'
    size = 24
    weight = 600,
})
-- Броня --
surface.CreateFont('armor', {
    font = 'Open Sans Bold'
    size = 24
    weight = 600,
})
-- Профессия --
surface.CreateFont('job', {
    font = 'Open Sans Bold'
    size = 24
    weight = 600,
})
-- Деньги --
surface.CreateFont('money', {
    font = 'Open Sans Bold'
    size = 24
    weight = 600,
})
-- Ком.Час --
surface.CreateFont('lockdown', {
    font = 'Open Sans Bold'
    size = 24
    weight = 600,
})
-- Розыск --
surface.CreateFont('wanted', {
    font = 'Open Sans Bold'
    size = 24
    weight = 600,
})
-- ЮзерГруп --
surface.CreateFont('usergroup', {
    font = 'Open Sans Bold'
    size = 24
    weight = 600,
})
-- Патроны1 --
surface.CreateFont('ammo1', {
    font = 'Open Sans Bold'
    size = 24
    weight = 600,
})
-- Патроны2 --
surface.CreateFont('ammo2', {
    font = 'Open Sans Bold'
    size = 24
    weight = 600,
})

--ХУД

local function ALPHAHUD()

-- Локальные Переменные --

    local ply = LocalPlyer()
    local salary = ply():getDarkRPVar ( 'salary' )
    local hp = LocalPlyer():Health() or 0
    local maxhp = LocalPlayer():GetMaxHealth() or 0
    local armor = ply():Armor() or 0
    local maxar = ply():GetMaxArmor() or 0
    local money = ply():getDarkRPVar( "money" )
    local job = ply():getDarkRPVar( "job" )
    local donate = ply():GetUserGroup()
    local lockdown = ply():GetGlobalBool( "DarkRP_LockDown" )
    local wanted = ply():getDarkRPVar( "wanted" )
    local wantedr = ply():getDarkRPVar ( "wantedReason" )
    
    draw.RoundedBox(11, x, y -60, 380, 180, Color (0, 0, 0, 254)


    draw.SimpleText('Имя : '..ply:Name(),'health', x + 4, y - 60,Color(255, 255, 255, 255),TEXT_ALIGN_LEFT,TEXT_ALIGN_TOP)

    draw.SimpleText('Здоровье : '..hp..'%'..' / '..maxhp..'%', 'health', x + 4, y - 35,Color(255, 255, 255, 255),TEXT_ALIGN_LEFT,TEXT_ALIGN_TOP)

    draw.SimpleText( 'Броня : '..armor..'%'..' / '..maxar..'%', 'health', x + 4, y - 10,Color(255, 255, 255, 255),TEXT_ALIGN_LEFT,TEXT_ALIGN_TOP)

    draw.SimpleText('Профессия : '..job, 'health', x + 4, y + 15,Color(255, 255, 255, 255),TEXT_ALIGN_LEFT,TEXT_ALIGN_TOP)

    draw.SimpleText('Деньги : $'..money, 'health' , x + 4, y + 40,Color(255 , 255, 255, 255),TEXT_ALIGN_LEFT,TEXT_ALIGN_TOP)

    if ( lockdown ) then  
    
                    draw.SimpleText('Коменданский Час! Вернитесь Домой!','health', x + 4, y + 65,Color(255, 255, 255, 255)TEXT_ALIGN_LEFT,TEXT_ALIGN_TOP)
    else
        return false
    end
    if ( wanted ) then
        draw.SimpleText('Вы в Розыске по причине : '..wantedr,'health', x + 4, y + 90,Color(255, 255, 255, 255)TEXT_ALIGN_LEFT,TEXT_ALIGN_TOP)
    else
        return false
    end
end

-- Добавление Хука --
hook.Add('HUDPaint', 'ALPHAHUD',ALPHAHUD)
