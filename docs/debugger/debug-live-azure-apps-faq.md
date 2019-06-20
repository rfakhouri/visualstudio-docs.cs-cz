---
title: Nejčastější dotazy k ladění snímků | Dokumentace Microsoftu
ms.date: 11/07/2017
ms.topic: reference
helpviewer_keywords:
- debugger
ms.assetid: 944f1eb0-a74b-4d28-ae2b-a370cd869add
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 315b24d384a1e3576af6590923c0e546785918ae
ms.sourcegitcommit: b468d71052a1b8a697f477ab23a3644de139f1e9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/19/2019
ms.locfileid: "67255992"
---
# <a name="frequently-asked-questions-for-snapshot-debugging-in-visual-studio"></a>Nejčastější dotazy k ladění snímků v sadě Visual Studio

Tady je seznam dotazů, ke kterým může při ladění pomocí ladicího programu snímků živé aplikace Azure.

#### <a name="what-is-the-performance-cost-of-taking-a-snapshot"></a>Co je náklady na pořízení snímku?

Pokud ladicí program snímků zachytí snímek vaší aplikace, větve proces aplikací a pozastaví rozvětveného kopírování. Při ladění snímku, kterou ladíte proti rozvětveného kopii procesu. Tento proces trvá jenom 10-20 MS ale nekopíruje haldě úplné aplikace. Místo toho zkopíruje pouze tabulky stránky a zkopírování při zápisu na stránkách. Pokud některé objekty vaší aplikace na změnu haldy příslušných stránkách s poté zkopírován. To je syrovátky jednotlivých snímků má malé v paměti náklady (v řádu stovek kB pro většinu aplikací).

#### <a name="what-happens-if-i-have-a-scaled-out-azure-app-service-multiple-instances-of-my-app"></a>Co se stane, když mám horizontálním navýšením kapacity služby Azure App Service (více instancí aplikace)?

Pokud máte více instancí vaší aplikace, snímkovacích bodů: použije na každý jednu instanci. Pouze první snímkovací bod k dosažení s podmínkami uvedenými vytvoří snímek. Pokud máte více snímkovacích bodů: novější snímky pocházet ze stejné instance, kterou vytvořili první snímek. Protokolovací body odesílané do okna výstup se zobrazí jen zprávy z jedné instance, zatímco odesílat protokoly aplikací protokolovacích bodů: odesílání zpráv z každé instance.

#### <a name="how-does-the-snapshot-debugger-load-symbols"></a>Jak Snapshot Debugger načíst symboly

Snapshot Debugger vyžaduje, abyste měli odpovídající symboly pro vaši aplikaci, místní nebo nasazenou do služby Azure App Service. (Vložené soubory PDB se momentálně nepodporují.) Snapshot Debugger automaticky stahuje symboly ze služby Azure App Service. Od verze Visual Studio 2017 verze 15.2, nasazení do služby Azure App Service také nasadí symboly vaší aplikace.

#### <a name="does-the-snapshot-debugger-work-against-release-builds-of-my-application"></a>Funguje Snapshot Debugger pro buildy vydaných verzí mojí aplikace?

Ano – Snapshot Debugger by měla fungovat pro buildy vydaných verzí. Pokud snímkovacího bodu je umístěn ve funkci, funkci přepsán zpět do ladicí verze, takže laditelný. Při zastavení ladicího programu snímků vrací funkce verze sestavení pro vydání.

#### <a name="can-logpoints-cause-side-effects-in-my-production-application"></a>Může způsobit protokolovacích bodů: vedlejší účinky v produkční aplikace?

Prakticky ne - vyhodnocují všechny zprávy protokolu, které přidáte do vaší aplikace. Ve vaší aplikaci se nemůže způsobit žádné vedlejší účinky. Některé vlastnosti nativní však nemusí být přístupný pomocí protokolovacích bodů.

#### <a name="does-the-snapshot-debugger-work-if-my-server-is-under-load"></a>Funguje Snapshot Debugger při zatížení serveru?

Ano, ladění snímků může fungovat pro servery v zatížení. Snapshot Debugger omezuje a nebude zachycení snímků v situacích, ve kterých je nízká množství volné paměti na serveru.

#### <a name="how-do-i-uninstall-the-snapshot-debugger"></a>Jak odinstaluji Snapshot Debugger?

Odinstalovat rozšíření pro Snapshot Debugger web ve službě App Service pomocí následujících kroků:

1. Vypněte službu App Service pomocí Průzkumníka cloudu v sadě Visual Studio nebo na webu Azure portal.
1. Přejděte na Web App Service Kudu (to znamená, yourappservice. **Správce řízení služeb**. azurewebsites.net) a přejděte do **rozšířením webu**.
1. Kliknutím na křížek v rozšíření webu pro Snapshot Debugger jeho odstranění.

#### <a name="why-are-ports-opened-during-a-snapshot-debugger-session"></a>Proč jsou otevřené porty během relace Snapshot Debugger?

Snapshot Debugger je potřeba otevřít sadu porty Pokud chcete ladit snímkům pořízeným v Azure, jde o stejné porty vyžadované pro vzdálené ladění. [Můžete najít seznam portů zde](../debugger/remote-debugger-port-assignments.md).

#### <a name="how-do-i-disable-the-remote-debugger-extension"></a>Jak zakázat rozšíření vzdálený ladicí program?

Pro App Service:
1. Zakážete rozšíření vzdálený ladicí program přes Azure portal pro službu App Service.
2. Azure portal > okno prostředek aplikace služby > *nastavení aplikace*
3. Přejděte *ladění* části a klikněte na tlačítko *vypnout* tlačítko pro *vzdálené ladění*.

Pro AKS:
1. Aktualizovat váš soubor Dockerfile odebrat oddíly odpovídající [Visual Studio Snapshot Debugger na imagích Dockeru](https://github.com/Microsoft/vssnapshotdebugger-docker).
2. Sestavili a upravenou image Dockeru.

Pro virtuální počítač nebo virtuální počítače škálovací sady odeberte rozšíření, certifikáty, KeyVaults a příchozí NAT fondů vzdálený ladicí program následujícím způsobem:

1. Odebrat rozšíření vzdáleného ladicího programu  

   Existuje několik způsobů, jak zakázat vzdálený ladicí program pro virtuální počítače a škálovací sady virtuálních počítačů:  

      - Zakažte vzdálený ladicí program pomocí Průzkumníka cloudu  

         - Cloud Explorer > prostředku vašeho virtuálního počítače > Zakázat ladění (Zakázání ladění neexistuje pro škálovací sady na Průzkumník cloudu virtuálních počítačů).  


      - Zakažte vzdálený ladicí program pomocí skriptů a rutin prostředí PowerShell  

         Pro virtuální počítač:  

         ```
         Remove-AzVMExtension -ResourceGroupName $rgName -VMName $vmName -Name Microsoft.VisualStudio.Azure.RemoteDebug.VSRemoteDebugger  
         ```

         Pro škálovací sady virtuálních počítačů:  
         ```
         $vmss = Get-AzVmss -ResourceGroupName $rgName -VMScaleSetName $vmssName  
         $extension = $vmss.VirtualMachineProfile.ExtensionProfile.Extensions | Where {$_.Name.StartsWith('VsDebuggerService')} | Select -ExpandProperty Name  
         Remove-AzVmssExtension -VirtualMachineScaleSet $vmss -Name $extension  
         ```

      - Zakažte vzdálený ladicí program na webu Azure portal
         - Azure portal > virtuální počítač nebo virtuální machine scale sets s okno prostředků > rozšíření  
         - Odinstalovat rozšíření Microsoft.VisualStudio.Azure.RemoteDebug.VSRemoteDebugger  


         > [!NOTE]
         > Škálovací sady virtuálních počítačů – portál neumožňuje odebrání DebuggerListener porty. Je potřeba použít Azure PowerShell. Podrobnosti najdete níže.
  
2. Odebrat certifikáty a Azure KeyVault

   Při instalaci rozšíření vzdálený ladicí program pro virtuální počítač nebo škálovací sady virtuálních počítačů, klientské a serverové certifikáty se vytváří za účelem ověření klienta VS s Azure Virtual Machine a virtual machine scale sets s prostředky.  

   - Klientský certifikát  

      Tento certifikát je podepsaný svým držitelem certifikátu uloženého v certifikátu: / CurrentUser/Moje /  

      ```
      Thumbprint                                Subject  
      ----------                                -------  

      1234123412341234123412341234123412341234  CN=ResourceName  
      ```

      Je možné odebrat tento certifikát z vašeho počítače přes PowerShell

      ```
      $ResourceName = 'ResourceName' # from above  
      Get-ChildItem -Path Cert:\CurrentUser\My | Where-Object {$_.Subject -match $ResourceName} | Remove-Item  
      ```

   - Certifikát serveru
      - Odpovídající kryptografický otisk certifikátu serveru je nasazená jako tajný kód do Azure Key Vaultu. VS. pokusí se vyhledat nebo vytvořit trezor klíčů s předponou MSVSAZ * v oblasti odpovídající virtuální počítač nebo škálovací sady virtuálních počítačů resource. Všechny virtuální počítače nebo virtuálního počítače škálovací sady prostředky nasazené do této oblasti se proto sdílet stejný trezor klíčů.  
      - Odstranění tajného klíče kryptografický otisk certifikátu serveru, přejděte na web Azure Portal a vyhledejte ve stejné oblasti, který je hostitelem vašeho prostředku KeyVault MSVSAZ *. Odstranění tajného klíče, které by měly být popsány `remotedebugcert<<ResourceName>>`  
      - Musíte také odstranit tajný klíč serveru z vašich prostředků pomocí Powershellu.  

      Pro virtuální počítače:  

      ```
      $vm.OSProfile.Secrets[0].VaultCertificates.Clear()  
      Update-AzVM -ResourceGroupName $rgName -VM $vm  
      ```
                        
      Pro škálovací sady virtuálních počítačů:  

      ```
      $vmss.VirtualMachineProfile.OsProfile.Secrets[0].VaultCertificates.Clear()  
      Update-AzVmss -ResourceGroupName $rgName -VMScaleSetName $vmssName -VirtualMachineScaleSet $vmss  
      ```
                        
3. Odeberte všechny fondy DebuggerListener příchozí NAT (škálovací sady virtuálních počítačů pouze)  

   Vzdálený ladicí program představuje fondy NAT ve vázané na DebuggerListener, které se použijí pro nástroj pro vyrovnávání zatížení vaší škálovací sadě.  

   ```
   $inboundNatPools = $vmss.VirtualMachineProfile.NetworkProfile.NetworkInterfaceConfigurations.IpConfigurations.LoadBalancerInboundNatPools  
   $inboundNatPools.RemoveAll({ param($pool) $pool.Id.Contains('inboundNatPools/DebuggerListenerNatPool-') }) | Out-Null  
                
   if ($LoadBalancerName)  
   {
      $lb = Get-AzLoadBalancer -ResourceGroupName $ResourceGroup -name $LoadBalancerName  
      $lb.FrontendIpConfigurations[0].InboundNatPools.RemoveAll({ param($pool) $pool.Id.Contains('inboundNatPools/DebuggerListenerNatPool-') }) | Out-Null  
      Set-AzLoadBalancer -LoadBalancer $lb  
   }
   ```

#### <a name="how-do-i-disable-snapshot-debugger"></a>Jak zakázat Snapshot Debugger?

Pro službu App Service:
1. Zakážete Snapshot Debugger pro službu App Service prostřednictvím portálu Azure portal.
2. Azure portal > okno prostředek aplikace služby > *nastavení aplikace*
3. Odstraňte následující nastavení aplikace na webu Azure Portal a uložte provedené změny. 
    - INSTRUMENTATIONENGINE_EXTENSION_VERSION
    - SNAPSHOTDEBUGGER_EXTENSION_VERSION

    > [!WARNING]
    > Všechny změny nastavení aplikace opraví, zahájí se restartování aplikace. Další informace o nastavení aplikace najdete v tématu [nakonfigurovat aplikaci služby App Service na webu Azure Portal](/azure/app-service/web-sites-configure).

Pro AKS:
1. Aktualizovat váš soubor Dockerfile odebrat oddíly odpovídající [Visual Studio Snapshot Debugger na imagích Dockeru](https://github.com/Microsoft/vssnapshotdebugger-docker).
2. Sestavili a upravenou image Dockeru.

Pro virtuální počítač nebo virtuální počítače škálovací sady:

Chcete-li zakázat Snapshot Debugger několika způsoby:
- Cloud Explorer > váš virtuální počítač nebo virtuální počítače škálovací sady prostředků > zakázat diagnostiku

- Azure portal > váš virtuální počítač nebo virtuální počítače škálovací sady okno prostředků > Rozšíření > Microsoft.Insights.VMDiagnosticsSettings odinstalace rozšíření

- Rutiny Powershellu z [Az Powershellu](https://docs.microsoft.com/powershell/azure/overview)

    Virtuální počítač:
    ```
        Remove-AzVMExtension -ResourceGroupName $rgName -VMName $vmName -Name Microsoft.Insights.VMDiagnosticsSettings 
    ```
    
    Škálovací sady virtuálních počítačů:
    ```
        $vmss = Get-AzVmss -ResourceGroupName $rgName -VMScaleSetName $vmssName
        Remove-AzVmssExtension -VirtualMachineScaleSet $vmss -Name Microsoft.Insights.VMDiagnosticsSettings
    ```

## <a name="see-also"></a>Viz také:

- [Ladění v sadě Visual Studio](../debugger/index.md)
- [Ladění živé aplikace v ASP.NET pomocí ladicího programu snímků](../debugger/debug-live-azure-applications.md)
- [Ladění za provozu technologie ASP.NET Azure Virtual Machines Machines\Virtual škálovací sady pomocí ladicího programu snímků](../debugger/debug-live-azure-virtual-machines.md)
- [Ladění za provozu technologie ASP.NET Kubernetes se službou Azure pomocí ladicího programu snímků](../debugger/debug-live-azure-kubernetes.md)
- [Řešení potíží a známé problémy pro ladění snímků](../debugger/debug-live-azure-apps-troubleshooting.md)