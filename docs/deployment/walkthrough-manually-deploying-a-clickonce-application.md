---
title: 'Návod: Ruční nasazení aplikace ClickOnce | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Mage.exe, manual ClickOnce deployments
- MageUI.exe, manual ClickOnce deployments
- deploying applications [ClickOnce], manual ClickOnce deployments
- ClickOnce deployment, manually
- ClickOnce deployment, SDK tools
- manual ClickOnce deployments
- manifests [ClickOnce]
ms.assetid: ccee6551-a1b9-4ca2-8845-9c1cf4ac2560
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 001aa8f3436e1594b198a81779c77258ca829a21
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-manually-deploying-a-clickonce-application"></a>Návod: Ruční nasazení aplikace ClickOnce
Pokud nemůžete použít Visual Studio k nasazení vaší [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace, nebo budete muset použít nasazení pokročilé funkce, jako je například nasazení důvěryhodných aplikací by měl použít nástroj příkazového řádku Mage.exe k vytvoření vašeho [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifesty. Tento návod popisuje, jak vytvořit [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení pomocí příkazového řádku verze (Mage.exe) nebo grafické verze (MageUI.exe) generování manifestu a nástroj pro úpravy.  
  
## <a name="prerequisites"></a>Požadavky  
 Tento názorný postup obsahuje některé požadavky a možnosti, které je třeba vybrat před vytvořením nasazení.  
  
-   Nainstalujte Mage.exe a MageUI.exe.  
  
     Mage.exe a MageUI.exe jsou součástí [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)]. Musí mít buď [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] nainstalována nebo verzi [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] zahrnutá v sadě Visual Studio. Další informace najdete v tématu [Windows SDK](http://go.microsoft.com/fwlink/?LinkId=158044) na webu MSDN.  
  
-   Zadejte aplikaci k nasazení.  
  
     Tento návod předpokládá, že máte aplikace Windows, která jste připravení nasadit. Tato aplikace bude označovány jako AppToDeploy.  
  
-   Zjistěte, jak budou distribuována nasazení.  
  
     Tyto možnosti distribuce: Web, sdílené složky nebo disku CD. Další informace najdete v tématu [ClickOnce – zabezpečení a nasazení](../deployment/clickonce-security-and-deployment.md).  
  
-   Určí, zda aplikace vyžaduje zvýšenou úroveň důvěryhodnosti.  
  
     Pokud vaše aplikace vyžaduje úplný vztah důvěryhodnosti – například plný přístup k systému uživatele – můžete použít `-TrustLevel` možnost Mage.exe nastavit. Pokud chcete definovat vlastní sadu pro aplikaci oprávnění, zkopírujte v Internetu nebo intranetu části oprávnění z jiného manifestu a upravit tak, aby vyhovovaly potřebám vaší ho přidat do manifest aplikace pomocí textového editoru nebo MageUI.exe. Další informace najdete v tématu [Přehled nasazení důvěryhodných aplikací](../deployment/trusted-application-deployment-overview.md).  
  
-   Získání certifikátu Authenticode.  
  
     Měli byste podepsat nasazení s certifikátem Authenticode. Testovací certifikát můžete vygenerovat pomocí nástrojů Visual Studio, MageUI.exe nebo MakeCert.exe a Pvk2Pfx.exe nebo certifikát můžete získat od certifikační autority (CA). Pokud se rozhodnete používat nasazení důvěryhodných aplikací, musíte také provést jednorázové instalaci certifikátu do všech klientských počítačů. Další informace najdete v tématu [Přehled nasazení důvěryhodných aplikací](../deployment/trusted-application-deployment-overview.md).  
  
    > [!NOTE]
    >  Můžete se přihlásit taky nasazení s certifikátem CNG, který můžete získat od certifikační autority.  
  
-   Ujistěte se, že aplikace nemá manifest s informacemi řízení uživatelských účtů.  
  
     Je nutné určit, jestli vaše aplikace obsahuje manifest s informacemi řízení uživatelských účtů (UAC), například `<dependentAssembly>` elementu. Chcete-li zkontrolovat manifest aplikace, můžete použít webu Windows Sysinternals [Sigcheck](http://go.microsoft.com/fwlink/?LinkId=158035) nástroj.  
  
     Pokud vaše aplikace obsahuje manifest s podrobnostmi nástroje Řízení uživatelských účtů, můžete jej znovu sestavit bez informací o řízení uživatelských účtů. Pro projekt C# v sadě Visual Studio otevřete vlastnosti projektu a vyberte kartu aplikace. V **Manifest** rozevíracího seznamu vyberte **vytvořit aplikaci bez manifestu**. Pro projekt jazyka Visual Basic v sadě Visual Studio, otevřete vlastnosti projektu, vyberte kartu aplikace a klikněte na tlačítko **nastavení nástroje Řízení uživatelských účtů zobrazení**. V otevřeném souboru manifestu, odeberte všechny elementy v rámci jednoho `<asmv1:assembly>` elementu.  
  
-   Určí, zda aplikace vyžaduje splnění požadavků na klientském počítači.  
  
     [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace nasazené ze sady Visual Studio mohou zahrnovat zavaděč instalace nezbytné součásti (setup.exe) v rámci vašeho nasazení. Tento návod vytvoří dva manifesty požadované pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení. Zaváděcí můžete vytvořit pomocí [GenerateBootstrapper – úloha](../msbuild/generatebootstrapper-task.md).  
  
### <a name="to-deploy-an-application-with-the-mageexe-command-line-tool"></a>Nasazení aplikace pomocí nástroje příkazového řádku Mage.exe  
  
1.  Vytvořte adresář, kam můžete ukládat vaše [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] soubory nasazení.  
  
2.  V adresáři nasazení, který jste právě vytvořili vytvořte podadresář verze. Pokud je při prvním nasazení aplikace, název podadresář verze **1.0.0.0**.  
  
    > [!NOTE]
    >  Verze vašeho nasazení může být odlišný od verze vaší aplikace.  
  
3.  Zkopírujte všechny soubory aplikace podadresář verze, včetně spustitelné soubory, sestavení, prostředky a datových souborů. V případě potřeby můžete vytvořit další podadresáře, které obsahují další soubory.  
  
4.  Otevřete [!INCLUDE[winsdkshort](../debugger/debug-interface-access/includes/winsdkshort_md.md)] nebo Visual Studio příkazového řádku a změňte podadresář verze.  
  
5.  Vytvořte manifest aplikace pomocí volání Mage.exe. Následující příkaz vytvoří manifest aplikace pro kód zkompilovaný pro spuštění na procesor Intel x86.  
  
    ```  
    mage -New Application -Processor x86 -ToFile AppToDeploy.exe.manifest -name "My App" -Version 1.0.0.0 -FromDirectory .   
    ```  
  
    > [!NOTE]
    >  Nezapomeňte použít tečku (.) po `-FromDirectory` možnost, která označuje aktuální adresář. Pokud nebudou obsahovat tečky, musíte zadat cestu k souborům aplikace.  
  
6.  Podepsání manifestu aplikace certifikátem Authenticode. Nahraďte *mycert.pfx* s cestou k souboru certifikátu. Nahraďte *hesel* s heslem pro váš soubor certifikátu.  
  
    ```  
    mage -Sign AppToDeploy.exe.manifest -CertFile mycert.pfx -Password passwd  
    ```  
  
     K podepsání manifestu aplikace s certifikátem CNG, použijte následující. Nahraďte *cngCert.pfx* s cestou k souboru certifikátu.  
  
    ```  
    mage -Sign AppToDeploy.exe.manifest -CertFile cngCert.pfx  
    ```  
  
7.  Změnit na kořenovém adresáři pro nasazení.  
  
8.  Generování manifestu nasazení s volání Mage.exe. Ve výchozím nastavení, Mage.exe označíte vaší [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení jako instalované aplikace, takže to můžete spustit online a offline. Chcete-li aplikace k dispozici jenom v případě, že uživatel je online, použijte `-Install` možnost s hodnotou `false`. Pokud používáte výchozí nastavení, a uživatelé nainstalují aplikace ze webové stránky nebo sdílené složky, ujistěte se, že hodnota `-ProviderUrl` možnost odkazuje na umístění aplikace manifestu na webový server nebo sdílené složky.  
  
    ```  
    mage -New Deployment -Processor x86 -Install true -Publisher "My Co." -ProviderUrl "\\myServer\myShare\AppToDeploy.application" -AppManifest 1.0.0.0\AppToDeploy.exe.manifest -ToFile AppToDeploy.application  
    ```  
  
9. Podepsání manifestu nasazení certifikátem Authenticode nebo CNG.  
  
    ```  
    mage -Sign AppToDeploy.application -CertFile mycert.pfx -Password passwd  
    ```  
  
     or  
  
    ```  
    mage -Sign AppToDeploy.exe.manifest -CertFile cngCert.pfx  
    ```  
  
10. Zkopírujte všechny soubory v adresáři pro nasazení do cíle nasazení nebo médium. To může být buď do složky na webu nebo serveru FTP, sdílené složky nebo disku CD-ROM.  
  
11. Uživatelům poskytnout adresu URL, UNC nebo fyzická média, které jsou potřebné k instalaci vaší aplikace. Pokud zadáte adresu URL nebo název cesty UNC, je třeba uživatelům zadat úplnou cestu manifestu nasazení. Například, pokud je AppToDeploy nasazena na http://webserver01/ v adresáři AppToDeploy by být úplná cesta URL http://webserver01/AppToDeploy/AppToDeploy.application.  
  
### <a name="to-deploy-an-application-with-the-mageuiexe-graphical-tool"></a>Nasazení aplikace pomocí grafického rozhraní nástroje MageUI.exe  
  
1.  Vytvořte adresář, kam můžete ukládat vaše [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] soubory nasazení.  
  
2.  V adresáři nasazení, který jste právě vytvořili vytvořte podadresář verze. Pokud je při prvním nasazení aplikace, název podadresář verze **1.0.0.0**.  
  
    > [!NOTE]
    >  Verze vašeho nasazení je pravděpodobně odlišná od verze vaší aplikace.  
  
3.  Zkopírujte všechny soubory aplikace podadresář verze, včetně spustitelné soubory, sestavení, prostředky a datových souborů. V případě potřeby můžete vytvořit další podadresáře, které obsahují další soubory.  
  
4.  Spusťte grafický nástroj MageUI.exe.  
  
    ```  
    MageUI.exe  
    ```  
  
5.  Vytvořit nové manifest aplikace výběrem **soubor**, **nový**, **Application Manifest** z nabídky.  
  
6.  Na výchozí **název** , zadejte název a verze počet toto nasazení. Zadat také **procesoru** vytvořené aplikace, jako je například x86.  
  
7.  Vyberte **soubory** kartě a klikněte na tlačítko se třemi tečkami (**...** ) vedle položky **adresář aplikace** textové pole. Zobrazí se dialogové okno Vyhledat složku.  
  
8.  Vyberte podadresář verze obsahující soubory aplikace a pak klikněte na tlačítko **OK**.  
  
9. Pokud nasadíte z Internetové informační služby (IIS), vyberte **po vyplnění přidat příponu .deploy do souboru, která ho nemá** zaškrtávací políčko.  
  
10. Klikněte **vyplnit** tlačítko Přidat do seznamu souborů pro všechny soubory aplikace. Pokud vaše aplikace obsahuje více než jeden spustitelný soubor, označte hlavní spustitelný soubor pro toto nasazení jako spouštěcí aplikaci tak, že vyberete **vstupní bod** z **typ souboru** rozevíracího seznamu. (Pokud vaše aplikace obsahuje pouze jeden spustitelný soubor, MageUI.exe ho označí za vás.)  
  
11. Vyberte **oprávněních** a vyberte úroveň důvěryhodnosti, je nutné, aby k vyhodnocení aplikace. Výchozí hodnota je **FullTrust**, která bude vhodná pro většinu aplikací.  
  
12. Vyberte **soubor**, **uložit jako** z nabídky. Zobrazí se možnosti podepisování dialogové okno s výzvou k podepsání manifestu aplikace.  
  
13. Pokud máte certifikát uložený jako soubor ve vašem systému souborů, použijte **podepsat se souborem certifikátu** možnost a vyberte certifikát ze systému souborů pomocí se třemi tečkami (**...** ) tlačítko. Pak zadejte heslo certifikátu.  
  
     -nebo-  
  
     Pokud je váš certifikát veden v úložišti certifikátů, které je přístupné z počítače, vyberte **přihlášení uložené certifikátem** a vyberte certifikát ze seznamu Zadaná možnost.  
  
14. Klikněte na tlačítko **OK** k podepsání manifestu aplikace. Zobrazí se dialogové okno Uložit jako.  
  
15. V dialogovém okně Uložit jako zadejte adresář verze a pak klikněte na tlačítko **Uložit**.  
  
16. Vyberte **soubor**, **nový**, **Manifest nasazení** z nabídky pro vytvoření manifestu nasazení.  
  
17. Na **název** kartě, zadejte název a verze číslo pro toto nasazení (**1.0.0.0** v tomto příkladu). Zadat také **procesoru** vytvořené aplikace, jako je například x86.  
  
18. Vyberte **popis** a zadejte hodnoty pro **vydavatele** a **produkt *** t**. (**Produktu** je název přidělený k aplikaci v nabídce Start při instalaci aplikace na klientský počítač pro použití v offline režimu.)  
  
19. Vyberte **možnosti nasazení** kartě a v **umístění spuštění** text pole, zadejte umístění manifestu aplikace na webovém serveru nebo sdílené složky. Například \\\myServer\myShare\AppToDeploy.application.  
  
20. Pokud jste přidali příponu .deploy v předchozím kroku, také vybrat možnost **používaly příponu názvu souboru .deploy** sem.  
  
21. Vyberte **možností aktualizace** kartě a určete, jak často tuto aplikaci aktualizovat. Pokud vaše aplikace používá <xref:System.Deployment.Application.UpdateCheckInfo> k vyhledání aktualizací, zrušte **této aplikace by měla vyhledat aktualizace** zaškrtávací políčko.  
  
22. Vyberte **odkaz aplikace** a pak klikněte **vyberte Manifest** tlačítko. Otevřené dialogové okno se zobrazí.  
  
23. Vyberte manifest aplikace, kterou jste dříve vytvořili a pak klikněte na tlačítko **otevřete**.  
  
24. Vyberte **soubor**, **uložit jako** z nabídky. Zobrazí se možnosti podepisování dialogové okno s výzvou k podepsání manifestu nasazení.  
  
25. Pokud máte certifikát uložený jako soubor ve vašem systému souborů, použijte **podepsat se souborem certifikátu** možnost a vyberte certifikát ze systému souborů pomocí se třemi tečkami (**...** ) tlačítko. Pak zadejte heslo certifikátu.  
  
     -nebo-  
  
     Pokud je váš certifikát veden v úložišti certifikátů, které je přístupné z počítače, vyberte **přihlášení uložené certifikátem** a vyberte certifikát ze seznamu Zadaná možnost.  
  
26. Klikněte na tlačítko **OK** pro podepsání manifestu nasazení. Zobrazí se dialogové okno Uložit jako.  
  
27. V **uložit jako** dialogové okno, přesunout nahoru do kořenového adresáře nasazení a pak klikněte na tlačítko **Uložit**.  
  
28. Zkopírujte všechny soubory v adresáři pro nasazení do cíle nasazení nebo médium. To může být buď do složky na webu nebo serveru FTP, sdílené složky nebo disku CD-ROM.  
  
29. Uživatelům poskytnout adresu URL, UNC nebo fyzická média, které jsou potřebné k instalaci vaší aplikace. Pokud zadáte adresu URL nebo název cesty UNC, je nutné zadat vaši uživatelé úplnou cestu manifest nasazení. Například, pokud je AppToDeploy nasazena na http://webserver01/ v adresáři AppToDeploy by být úplná cesta URL http://webserver01/AppToDeploy/AppToDeploy.application.  
  
## <a name="next-steps"></a>Další kroky  
 Pokud potřebujete nasadit novou verzi aplikace, vytvořte nový adresář s názvem po na novou verzi – například 1.0.0.1 — a zkopírujte soubory nové aplikace do nového adresáře. Dále musíte postupujte podle předchozích kroků k vytvoření a podepsání manifestu, nové aplikace a aktualizovat a podepsání manifestu nasazení. Nezapomeňte zadat stejnou vyšší verzi v obou Mage.exe `-New` a `-Update` volání, jako [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aktualizuje s celým číslem nejvíce vlevo, která je nejdůležitější pouze vyšší verze. Pokud jste použili MageUI.exe, můžete aktualizovat manifest nasazení otevřením, vyberete **odkaz aplikace** kartě, kliknutím na **vyberte Manifest** tlačítko a pak vybrat aktualizaci manifest aplikace.  
  
## <a name="see-also"></a>Viz také  
 [Mage.exe (generování manifestu a nástroj pro úpravy)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe (generování manifestu a nástroj pro úpravy, grafický klient)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)   
 [Publikování aplikací ClickOnce](../deployment/publishing-clickonce-applications.md)   
 [ClickOnce – Manifest nasazení](../deployment/clickonce-deployment-manifest.md)   
 [ClickOnce – manifest aplikace ](../deployment/clickonce-application-manifest.md)