# azure-firewall-vwan-multipip
Raw testing logs from using customer-managed PiPs at scale on AZFW in VWAN Hub

# Create prefixes (16 IP per /28 prefix)
```
az network public-ip prefix create --length 28 --location westeurope --name prefix1 --resource-group avs-ri
az network public-ip prefix create --length 28 --location westeurope --name prefix2 --resource-group avs-ri
az network public-ip prefix create --length 28 --location westeurope --name prefix3 --resource-group avs-ri
az network public-ip prefix create --length 28 --location westeurope --name prefix4 --resource-group avs-ri
az network public-ip prefix create --length 28 --location westeurope --name prefix5 --resource-group avs-ri
az network public-ip prefix create --length 28 --location westeurope --name prefix6 --resource-group avs-ri
az network public-ip prefix create --length 28 --location westeurope --name prefix7 --resource-group avs-ri
```

# Create Public IP from prefixes (111 Public IP total)
```
$prefix = Get-AzPublicIpPrefix -ResourceGroupName avs-ri -Name prefix
New-AzPublicIpAddress -Name "pip1" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip2" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip3" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip4" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip5" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip6" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip7" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip8" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip9" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip10" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip11" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip12" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip13" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip14" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip15" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip16" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix

$prefix = Get-AzPublicIpPrefix -ResourceGroupName avs-ri -Name prefix2
New-AzPublicIpAddress -Name "pip17" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip18" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip19" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip20" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip21" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip22" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip23" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip24" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip25" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip26" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip27" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip28" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip29" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip30" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip31" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip32" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix

$prefix = Get-AzPublicIpPrefix -ResourceGroupName avs-ri -Name prefix3
New-AzPublicIpAddress -Name "pip33" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip34" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip35" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip36" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip37" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip38" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip39" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip40" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip41" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip42" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip43" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip44" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip45" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip46" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip47" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip48" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix

$prefix = Get-AzPublicIpPrefix -ResourceGroupName avs-ri -Name prefix4
New-AzPublicIpAddress -Name "pip49" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip50" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip51" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip52" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip53" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip54" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip55" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip56" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip57" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip58" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip59" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip60" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip61" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip62" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip63" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix

$prefix = Get-AzPublicIpPrefix -ResourceGroupName avs-ri -Name prefix5
New-AzPublicIpAddress -Name "pip64" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip65" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip66" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip67" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip68" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip69" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip70" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip71" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip72" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip73" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip74" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip75" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip76" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip77" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip78" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip79" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix

$prefix = Get-AzPublicIpPrefix -ResourceGroupName avs-ri -Name prefix6
New-AzPublicIpAddress -Name "pip80" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip81" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip82" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip83" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip84" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip85" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip86" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip87" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip88" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip89" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip90" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip91" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip92" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip93" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip94" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip95" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix

$prefix = Get-AzPublicIpPrefix -ResourceGroupName avs-ri -Name prefix7
New-AzPublicIpAddress -Name "pip96" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip97" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip98" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip99" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip100" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip101" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip102" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip103" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip104" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip105" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip106" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip107" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip108" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip109" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip110" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
New-AzPublicIpAddress -Name "pip111" -ResourceGroupName "avs-ri" -Sku "Standard" -Location "westeurope" -AllocationMethod Static -PublicIpPrefix $prefix
```

# Create Azure Firewall in pre-existing VWAN Hub with 111 customer-managed PiPs
```
$pip1 = Get-AzPublicIpAddress -Name "pip1" -ResourceGroupName "avs-ri"
$pip2 = Get-AzPublicIpAddress -Name "pip2" -ResourceGroupName "avs-ri"
$pip3 = Get-AzPublicIpAddress -Name "pip3" -ResourceGroupName "avs-ri"
$pip4 = Get-AzPublicIpAddress -Name "pip4" -ResourceGroupName "avs-ri"
$pip5 = Get-AzPublicIpAddress -Name "pip5" -ResourceGroupName "avs-ri"
$pip6 = Get-AzPublicIpAddress -Name "pip6" -ResourceGroupName "avs-ri"
$pip7 = Get-AzPublicIpAddress -Name "pip7" -ResourceGroupName "avs-ri"
$pip8 = Get-AzPublicIpAddress -Name "pip8" -ResourceGroupName "avs-ri"
$pip9 = Get-AzPublicIpAddress -Name "pip9" -ResourceGroupName "avs-ri"
$pip10 = Get-AzPublicIpAddress -Name "pip10" -ResourceGroupName "avs-ri"
$pip11 = Get-AzPublicIpAddress -Name "pip11" -ResourceGroupName "avs-ri"
$pip12 = Get-AzPublicIpAddress -Name "pip12" -ResourceGroupName "avs-ri"
$pip13 = Get-AzPublicIpAddress -Name "pip13" -ResourceGroupName "avs-ri"
$pip14 = Get-AzPublicIpAddress -Name "pip14" -ResourceGroupName "avs-ri"
$pip15 = Get-AzPublicIpAddress -Name "pip15" -ResourceGroupName "avs-ri"
$pip16 = Get-AzPublicIpAddress -Name "pip16" -ResourceGroupName "avs-ri"
$pip17 = Get-AzPublicIpAddress -Name "pip17" -ResourceGroupName "avs-ri"
$pip18 = Get-AzPublicIpAddress -Name "pip18" -ResourceGroupName "avs-ri"
$pip19 = Get-AzPublicIpAddress -Name "pip19" -ResourceGroupName "avs-ri"
$pip20 = Get-AzPublicIpAddress -Name "pip20" -ResourceGroupName "avs-ri"
$pip21 = Get-AzPublicIpAddress -Name "pip21" -ResourceGroupName "avs-ri"
$pip22 = Get-AzPublicIpAddress -Name "pip22" -ResourceGroupName "avs-ri"
$pip23 = Get-AzPublicIpAddress -Name "pip23" -ResourceGroupName "avs-ri"
$pip24 = Get-AzPublicIpAddress -Name "pip24" -ResourceGroupName "avs-ri"
$pip25 = Get-AzPublicIpAddress -Name "pip25" -ResourceGroupName "avs-ri"
$pip26 = Get-AzPublicIpAddress -Name "pip26" -ResourceGroupName "avs-ri"
$pip27 = Get-AzPublicIpAddress -Name "pip27" -ResourceGroupName "avs-ri"
$pip28 = Get-AzPublicIpAddress -Name "pip28" -ResourceGroupName "avs-ri"
$pip29 = Get-AzPublicIpAddress -Name "pip29" -ResourceGroupName "avs-ri"
$pip30 = Get-AzPublicIpAddress -Name "pip30" -ResourceGroupName "avs-ri"
$pip31 = Get-AzPublicIpAddress -Name "pip31" -ResourceGroupName "avs-ri"
$pip32 = Get-AzPublicIpAddress -Name "pip32" -ResourceGroupName "avs-ri"
$pip33 = Get-AzPublicIpAddress -Name "pip33" -ResourceGroupName "avs-ri"
$pip34 = Get-AzPublicIpAddress -Name "pip34" -ResourceGroupName "avs-ri"
$pip35 = Get-AzPublicIpAddress -Name "pip35" -ResourceGroupName "avs-ri"
$pip36 = Get-AzPublicIpAddress -Name "pip36" -ResourceGroupName "avs-ri"
$pip37 = Get-AzPublicIpAddress -Name "pip37" -ResourceGroupName "avs-ri"
$pip38 = Get-AzPublicIpAddress -Name "pip38" -ResourceGroupName "avs-ri"
$pip39 = Get-AzPublicIpAddress -Name "pip39" -ResourceGroupName "avs-ri"
$pip40 = Get-AzPublicIpAddress -Name "pip40" -ResourceGroupName "avs-ri"
$pip41 = Get-AzPublicIpAddress -Name "pip41" -ResourceGroupName "avs-ri"
$pip42 = Get-AzPublicIpAddress -Name "pip42" -ResourceGroupName "avs-ri"
$pip43 = Get-AzPublicIpAddress -Name "pip43" -ResourceGroupName "avs-ri"
$pip44 = Get-AzPublicIpAddress -Name "pip44" -ResourceGroupName "avs-ri"
$pip45 = Get-AzPublicIpAddress -Name "pip45" -ResourceGroupName "avs-ri"
$pip46 = Get-AzPublicIpAddress -Name "pip46" -ResourceGroupName "avs-ri"
$pip47 = Get-AzPublicIpAddress -Name "pip47" -ResourceGroupName "avs-ri"
$pip48 = Get-AzPublicIpAddress -Name "pip48" -ResourceGroupName "avs-ri"
$pip49 = Get-AzPublicIpAddress -Name "pip49" -ResourceGroupName "avs-ri"
$pip50 = Get-AzPublicIpAddress -Name "pip50" -ResourceGroupName "avs-ri"
$pip51 = Get-AzPublicIpAddress -Name "pip51" -ResourceGroupName "avs-ri"
$pip52 = Get-AzPublicIpAddress -Name "pip52" -ResourceGroupName "avs-ri"
$pip53 = Get-AzPublicIpAddress -Name "pip53" -ResourceGroupName "avs-ri"
$pip54 = Get-AzPublicIpAddress -Name "pip54" -ResourceGroupName "avs-ri"
$pip55 = Get-AzPublicIpAddress -Name "pip55" -ResourceGroupName "avs-ri"
$pip56 = Get-AzPublicIpAddress -Name "pip56" -ResourceGroupName "avs-ri"
$pip57 = Get-AzPublicIpAddress -Name "pip57" -ResourceGroupName "avs-ri"
$pip58 = Get-AzPublicIpAddress -Name "pip58" -ResourceGroupName "avs-ri"
$pip59 = Get-AzPublicIpAddress -Name "pip59" -ResourceGroupName "avs-ri"
$pip60 = Get-AzPublicIpAddress -Name "pip60" -ResourceGroupName "avs-ri"
$pip61 = Get-AzPublicIpAddress -Name "pip61" -ResourceGroupName "avs-ri"
$pip62 = Get-AzPublicIpAddress -Name "pip62" -ResourceGroupName "avs-ri"
$pip63 = Get-AzPublicIpAddress -Name "pip63" -ResourceGroupName "avs-ri"
$pip64 = Get-AzPublicIpAddress -Name "pip64" -ResourceGroupName "avs-ri"
$pip65 = Get-AzPublicIpAddress -Name "pip65" -ResourceGroupName "avs-ri"
$pip66 = Get-AzPublicIpAddress -Name "pip66" -ResourceGroupName "avs-ri"
$pip67 = Get-AzPublicIpAddress -Name "pip67" -ResourceGroupName "avs-ri"
$pip68 = Get-AzPublicIpAddress -Name "pip68" -ResourceGroupName "avs-ri"
$pip69 = Get-AzPublicIpAddress -Name "pip69" -ResourceGroupName "avs-ri"
$pip70 = Get-AzPublicIpAddress -Name "pip70" -ResourceGroupName "avs-ri"
$pip71 = Get-AzPublicIpAddress -Name "pip71" -ResourceGroupName "avs-ri"
$pip72 = Get-AzPublicIpAddress -Name "pip72" -ResourceGroupName "avs-ri"
$pip73 = Get-AzPublicIpAddress -Name "pip73" -ResourceGroupName "avs-ri"
$pip74 = Get-AzPublicIpAddress -Name "pip74" -ResourceGroupName "avs-ri"
$pip75 = Get-AzPublicIpAddress -Name "pip75" -ResourceGroupName "avs-ri"
$pip76 = Get-AzPublicIpAddress -Name "pip76" -ResourceGroupName "avs-ri"
$pip77 = Get-AzPublicIpAddress -Name "pip77" -ResourceGroupName "avs-ri"
$pip78 = Get-AzPublicIpAddress -Name "pip78" -ResourceGroupName "avs-ri"
$pip79 = Get-AzPublicIpAddress -Name "pip79" -ResourceGroupName "avs-ri"
$pip80 = Get-AzPublicIpAddress -Name "pip80" -ResourceGroupName "avs-ri"
$pip81 = Get-AzPublicIpAddress -Name "pip81" -ResourceGroupName "avs-ri"
$pip82 = Get-AzPublicIpAddress -Name "pip82" -ResourceGroupName "avs-ri"
$pip83 = Get-AzPublicIpAddress -Name "pip83" -ResourceGroupName "avs-ri"
$pip84 = Get-AzPublicIpAddress -Name "pip84" -ResourceGroupName "avs-ri"
$pip85 = Get-AzPublicIpAddress -Name "pip85" -ResourceGroupName "avs-ri"
$pip86 = Get-AzPublicIpAddress -Name "pip86" -ResourceGroupName "avs-ri"
$pip87 = Get-AzPublicIpAddress -Name "pip87" -ResourceGroupName "avs-ri"
$pip88 = Get-AzPublicIpAddress -Name "pip88" -ResourceGroupName "avs-ri"
$pip89 = Get-AzPublicIpAddress -Name "pip89" -ResourceGroupName "avs-ri"
$pip90 = Get-AzPublicIpAddress -Name "pip90" -ResourceGroupName "avs-ri"
$pip91 = Get-AzPublicIpAddress -Name "pip91" -ResourceGroupName "avs-ri"
$pip92 = Get-AzPublicIpAddress -Name "pip92" -ResourceGroupName "avs-ri"
$pip93 = Get-AzPublicIpAddress -Name "pip93" -ResourceGroupName "avs-ri"
$pip94 = Get-AzPublicIpAddress -Name "pip94" -ResourceGroupName "avs-ri"
$pip95 = Get-AzPublicIpAddress -Name "pip95" -ResourceGroupName "avs-ri"
$pip96 = Get-AzPublicIpAddress -Name "pip96" -ResourceGroupName "avs-ri"
$pip97 = Get-AzPublicIpAddress -Name "pip97" -ResourceGroupName "avs-ri"
$pip98 = Get-AzPublicIpAddress -Name "pip98" -ResourceGroupName "avs-ri"
$pip99 = Get-AzPublicIpAddress -Name "pip99" -ResourceGroupName "avs-ri"
$pip100 = Get-AzPublicIpAddress -Name "pip100" -ResourceGroupName "avs-ri"
$pip101 = Get-AzPublicIpAddress -Name "pip101" -ResourceGroupName "avs-ri"
$pip102 = Get-AzPublicIpAddress -Name "pip102" -ResourceGroupName "avs-ri"
$pip103 = Get-AzPublicIpAddress -Name "pip103" -ResourceGroupName "avs-ri"
$pip104 = Get-AzPublicIpAddress -Name "pip104" -ResourceGroupName "avs-ri"
$pip105 = Get-AzPublicIpAddress -Name "pip105" -ResourceGroupName "avs-ri"
$pip106 = Get-AzPublicIpAddress -Name "pip106" -ResourceGroupName "avs-ri"
$pip107 = Get-AzPublicIpAddress -Name "pip107" -ResourceGroupName "avs-ri"
$pip108 = Get-AzPublicIpAddress -Name "pip108" -ResourceGroupName "avs-ri"
$pip109 = Get-AzPublicIpAddress -Name "pip109" -ResourceGroupName "avs-ri"
$pip110 = Get-AzPublicIpAddress -Name "pip110" -ResourceGroupName "avs-ri"
$pip111 = Get-AzPublicIpAddress -Name "pip111" -ResourceGroupName "avs-ri"
```
```
$fp = Get-AzFirewallPolicy -Name premium -ResourceGroupName avs-ri
$fpId = $fp.Id
$vHub = Get-AzVirtualHub -Name "hub-uks" -ResourceGroupName "avs-ri"
$vHubId = $vHub.Id

New-AzFirewall -Name "vwanfw" -ResourceGroupName "avs-ri" -Location westeurope -SkuTier "Premium" -SkuName "AZFW_Hub" -VirtualHubId $vHubId   -PublicIpAddress @($pip1, $pip2, $pip3, $pip4, $pip5, $pip6, $pip7, $pip8, $pip9, $pip10, $pip11, $pip12, $pip13, $pip14, $pip15, $pip16, $pip17, $pip18, $pip19, $pip20, $pip21, $pip22, $pip23, $pip24, $pip25, $pip26, $pip27, $pip28, $pip29, $pip30, $pip31, $pip32, $pip33, $pip34, $pip35, $pip36, $pip37, $pip38, $pip39, $pip40, $pip41, $pip42, $pip43, $pip44, $pip45, $pip46, $pip47, $pip48, $pip49, $pip50, $pip51, $pip52, $pip53, $pip54, $pip55, $pip56, $pip57, $pip58, $pip59, $pip60, $pip61, $pip62, $pip63, $pip64, $pip65, $pip66, $pip67, $pip68, $pip69, $pip70, $pip71, $pip72, $pip73, $pip74, $pip75, $pip76, $pip77, $pip78, $pip79, $pip80, $pip81, $pip82, $pip83, $pip84, $pip85, $pip86, $pip87, $pip88, $pip89, $pip90, $pip91, $pip92, $pip93, $pip94, $pip95, $pip96, $pip97, $pip98, $pip99, $pip100, $pip101, $pip102, $pip103, $pip104, $pip105, $pip106, $pip107, $pip108, $pip109, $pip110, $pip111)
```

> This took 10 minutes to complete deployment
  
 

