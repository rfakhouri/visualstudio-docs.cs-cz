---
title: Vytváření aplikací ClickOnce z příkazového řádku | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: conceptual
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- ClickOnce deployment, from command line
- publishing
- publishing, ClickOnce
ms.assetid: d9bc6212-c584-4f72-88c9-9a4b998c555e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 4488f32b135d766f494bc94946fbf77d42eb1e95
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31566183"
---
# <a name="building-clickonce-applications-from-the-command-line"></a>Vytváření aplikací ClickOnce z příkazového řádku
V [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)], můžete vytvořit projekty z příkazového řádku, i když jsou vytvořeny v integrované vývojové prostředí (IDE). Ve skutečnosti můžete znovu sestavit projekt s [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] na jiném počítači, který je k dispozici pouze [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] nainstalována. To umožňuje reprodukci sestavení pomocí automatizovaného procesu, například v Centrální sestavení testovacího prostředí nebo pomocí pokročilých skriptovacích technik nad rámec sestavení projektu sám sebe.  
  
## <a name="using-msbuild-to-reproduce-clickonce-application-deployments"></a>Pomocí nástroje MSBuild reprodukci nasazení aplikace ClickOnce  
 Při vyvolání msbuild/target: publish na příkazovém řádku, se říká MSBuild systému se projekt sestavil a vytvořit [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace ve složce publikování. To odpovídá výběru **publikovat** příkazu v prostředí IDE.  
  
 Tento příkaz spustí msbuild.exe, který je v cestě v příkazovém řádku prostředí Visual Studio.  
  
 "Cíl" je o tom, jak zpracovat příkaz indikátorem pro MSBuild. Klíčové cíle jsou cíl "sestavení" a "publikovat" cíle. Cíl sestavení se o ekvivalent výběr sestavení příkazu (nebo stiskněte F5) v prostředí IDE. Pokud chcete vytvořit projekt, můžete toho dosáhnout zadáním `msbuild`. Tento příkaz lze použít, protože cíl sestavení je výchozí cíl pro všechny projekty generované [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]. To znamená, že není nutné explicitně zadat cíl sestavení. Proto zadáním `msbuild` je stejné operace jako zadáním `msbuild /target:build`.  
  
 `/target:publish` Dává pokyn pro MSBuild vyvolání cíl publikování. Cíl publikování závisí na cíl sestavení. To znamená, že operace publikování je nadmnožinou operace sestavení. Například pokud jste provedli změnu mezi zdrojové soubory vašeho Visual Basic a C#, odpovídající sestavení by automaticky znovu sestaven pomocí operace publikování.  
  
 Informace o generování úplného [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení pomocí nástroje příkazového řádku Mage.exe k vytvoření vašeho [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifestu najdete v tématu [návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md).  
  
## <a name="creating-and-building-a-basic-clickonce-application-using-msbuild"></a>Vytváření a vytváření základní aplikace ClickOnce pomocí nástroje MSBuild  
  
#### <a name="to-create-and-publish-a-clickonce-project"></a>Vytvoření a publikování projektu ClickOnce  
  
1.  Klikněte na tlačítko **nový projekt** z **souboru** nabídky. **Nový projekt** zobrazí se dialogové okno.  
  
2.  Vyberte **aplikace Windows** a pojmenujte ji `CmdLineDemo`.  
  
3.  Z **sestavení** nabídky, klikněte na tlačítko **publikovat** příkaz.  
  
     Tento krok zajistí, že projekt správně nakonfigurován k vytvoření [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení aplikace.  
  
     Zobrazí se v Průvodci publikováním.  
  
4.  V Průvodci publikováním klikněte na **Dokončit**.  
  
     Visual Studio vygeneruje a zobrazí výchozí webové stránky, nazvanou Publish.htm.  
  
5.  Uložte projekt a poznamenejte si umístění složky, ve kterém je uložený.  
  
 Vytvoření výše uvedených kroků [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] projektu, který byl publikován první. Nyní můžete reprodukovat sestavení mimo prostředí IDE.  
  
#### <a name="to-reproduce-the-build-from-the-command-line"></a>Pro reprodukci sestavení z příkazového řádku  
  
1.  Ukončení [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)].  
  
2.  Z Windows **spustit** nabídky, klikněte na tlačítko **všechny programy**, pak **Microsoft Visual Studio**, pak **nástroje sady Visual Studio**, pak **Příkazového řádku visual studia**. To by měl otevřete příkazový řádek v kořenové složce aktuálního uživatele.  
  
3.  V **Visual Studio – příkazový řádek**, změňte aktuální adresář na umístění projektu, který jste právě vytvořili. Můžete například zadat `chdir My Documents\Visual Studio\Projects\CmdLineDemo`.  
  
4.  Chcete-li odebrat existující soubory vytvořené v "k vytvoření a publikování [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] projektu" typ `rmdir /s publish`.  
  
     Tento krok je volitelný, ale zajišťuje, že nové soubory byly všechny vyprodukované sestavení příkazového řádku.  
  
5.  Typ `msbuild /target:publish`.  
  
 Výše uvedené kroky zajistí úplné [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení aplikace v podsložce projektu s názvem P**publikovat**. CmdLineDemo.application je [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] – manifest nasazení. Složka CmdLineDemo_1.0.0.0 obsahuje soubory CmdLineDemo.exe a CmdLineDemo.exe.manifest [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifest aplikace. Setup.exe je zaváděcí nástroj, který ve výchozím nastavení je nastavena k instalaci [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. DotNetFX obsahuje redistribuovatelnosti pro [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]. Toto je celou sadu souborů je třeba nasadit aplikace na webu nebo prostřednictvím UNC nebo CD nebo DVD.  
  
## <a name="publishing-properties"></a>Vlastnosti publikování  
 Když publikujete aplikaci ve výše uvedených postupů, jsou následující vlastnosti vložit do souboru projektu v Průvodci publikováním. Tyto vlastnosti přímo ovlivňují jak [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] vytváří aplikace.  
  
 V CmdLineDemo.vbproj / CmdLineDemo.csproj:  
  
```  
<AssemblyOriginatorKeyFile>WindowsApplication3.snk</AssemblyOriginatorKeyFile>  
<GenerateManifests>true</GenerateManifests>  
<TargetZone>LocalIntranet</TargetZone>  
<PublisherName>Microsoft</PublisherName>  
<ProductName>CmdLineDemo</ProductName>  
<PublishUrl>http://localhost/CmdLineDemo</PublishUrl>  
<Install>true</Install>  
<ApplicationVersion>1.0.0.*</ApplicationVersion>  
<ApplicationRevision>1</ApplicationRevision>  
<UpdateEnabled>true</UpdateEnabled>  
<UpdateRequired>false</UpdateRequired>  
<UpdateMode>Foreground</UpdateMode>  
<UpdateInterval>7</UpdateInterval>  
<UpdateIntervalUnits>Days</UpdateIntervalUnits>  
<UpdateUrlEnabled>false</UpdateUrlEnabled>  
<IsWebBootstrapper>true</IsWebBootstrapper>  
<BootstrapperEnabled>true</BootstrapperEnabled>  
```  
  
 Některé z těchto vlastností na příkazovém řádku můžete přepsat beze změny samotný soubor projektu. Například následující staví [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení aplikace bez zaváděcího nástroje:  
  
```  
msbuild /target:publish /property:BootstrapperEnabled=false  
```  
  
 Vlastnosti publikování jsou řízeny v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] z **publikovat**, **zabezpečení**, a **podpisování** stránek vlastností **Návrhář projektu** . Níže je uveden popis publikování vlastností spolu s údajem o každé nastavení na různých stránkách vlastnosti návrháře aplikací:  
  
-   `AssemblyOriginatorKeyFile` Určuje soubor klíče používaný k podepisování vaší [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifestů aplikace. Stejný klíč lze také přiřadit vaše sestavení silným názvem. Tato vlastnost nastavena na **podpisování** stránky **Návrhář projektu**.  
  
 Následující vlastnosti jsou nastaveny na **zabezpečení** stránky:  
  
-   **Povolení nastavení zabezpečení ClickOnce** Určuje, zda [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifesty se generují. Při vytvoření projektu, [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] generování manifestu ve výchozím nastavení je vypnuto. Průvodce automaticky zapnout tento příznak na při publikování poprvé.  
  
-   **TargetZone** určuje úroveň důvěryhodnosti do vaší [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifest aplikace. Možné hodnoty jsou "Internet", "LocalIntranet" a "Vlastní". Internet a LocalIntranet způsobí, že výchozí nastavení do oprávnění vaší [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifest aplikace. LocalIntranet je výchozí nastavení a v podstatě znamená úplný vztah důvěryhodnosti. Určuje, že pouze oprávnění explicitně uvedené v souboru základní app.manifest do [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifest aplikace. Soubor app.manifest je částečné soubor manifestu, který obsahuje jenom definice, informace o vztahu důvěryhodnosti. Je skrytý soubor, automaticky přidá do projektu při konfiguraci oprávnění na **zabezpečení** stránky.  
  
 Následující vlastnosti jsou nastaveny na **publikovat** stránky:  
  
-   `PublishUrl` je umístění, kde aplikace bude publikována v prostředí IDE. Je vložen do [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifest aplikace, pokud `InstallUrl` nebo `UpdateUrl` je zadána vlastnost.  
  
-   `ApplicationVersion` Určuje verzi [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace. Toto je verze čtyřmístné číslo. Pokud je poslední číslice "*", pak se `ApplicationRevision` je nahrazena hodnotou vloženou do manifestu v čase vytvoření buildu.  
  
-   `ApplicationRevision` Určuje revizi. Toto je celé číslo, které zvýší pokaždé, když publikujete v prostředí IDE. Všimněte si, že není automaticky zvýšen pro sestavení prováděná v příkazovém řádku.  
  
-   `Install` Určuje, zda je nainstalovaná aplikace nebo spustit z webové aplikace.  
  
-   `InstallUrl` (není vidět) je umístění, kde budou uživatelé instalovat aplikace z. -Li zadána, tato hodnota je zapsaný do zaváděcího nástroje setup.exe, pokud `IsWebBootstrapper` vlastnost povolena. Je rovněž vložen do manifestu aplikace, pokud `UpdateUrl` není zadán.  
  
-   `SupportUrl` (není vidět) je umístění propojené v **přidat nebo odebrat programy** dialogové okno pro nainstalované aplikace.  
  
 Následující vlastnosti jsou nastaveny **aktualizace aplikace** dialogové okno, k němu přistupovat z **publikovat** stránky.  
  
-   `UpdateEnabled` Určuje, zda by měla aplikace vyhledat aktualizace.  
  
-   `UpdateMode` Určuje aktualizace na popředí nebo pozadí aktualizace.  
  
-   `UpdateInterval` Určuje, jak často by měla aplikace vyhledat aktualizace.  
  
-   `UpdateIntervalUnits` Určuje, zda `UpdateInterval` hodnota je jednotek hodiny, dny nebo týdny.  
  
-   `UpdateUrl` (není vidět) je umístění, ze kterého bude aplikace přijímat aktualizace. -Li zadána, tato hodnota je vložen do manifestu aplikace.  
  
-   Následující vlastnosti jsou nastaveny **možnosti publikování** dialogové okno, k němu přistupovat z **publikovat** stránky.  
  
-   `PublisherName` Určuje název vydavatele zobrazený ve výzvě zobrazené při instalaci nebo spuštění aplikace. V případě instalované aplikace, je také použít k zadání názvu složky na **spustit** nabídky.  
  
-   `ProductName` Určuje název produktu zobrazený ve výzvě zobrazené při instalaci nebo spuštění aplikace. V případě instalované aplikace, je také použít k zadání názvu odkazu na **spustit** nabídky.  
  
-   Následující vlastnosti jsou nastaveny **požadavky** dialogové okno, k němu přistupovat z **publikovat** stránky.  
  
-   `BootstrapperEnabled` Určuje, jestli se má generovat zavaděč setup.exe.  
  
-   `IsWebBootstrapper` Určuje, zda zaváděcí nástroj setup.exe funguje na webu nebo v režimu založené na disku.  
  
## <a name="installurl-supporturl-publishurl-and-updateurl"></a>InstallURL, SupportUrl, PublishURL a UpdateURL  
 Následující tabulka znázorňuje čtyři možnosti adresu URL pro ClickOnce – nasazení.  
  
|Možnost adresy URL|Popis|  
|----------------|-----------------|  
|`PublishURL`|Vyžaduje, pokud publikujete aplikaci ClickOnce pro webovou stránku.|  
|`InstallURL`|Volitelné. Tato adresa URL možnost nastavte, pokud se liší od instalace lokality `PublishURL`. Například můžete nastavit `PublishURL` skupinu a cesta k serveru FTP `InstallURL` na adresu URL webu.|  
|`SupportURL`|Volitelné. Tato adresa URL možnost nastavte, pokud se liší od webu podpory `PublishURL`. Například můžete nastavit `SupportURL` na webu podpory společnosti zákazníka.|  
|`UpdateURL`|Volitelné. Tato adresa URL možnost nastavte, pokud se liší od umístění aktualizace `InstallURL`. Například můžete nastavit `PublishURL` skupinu a cesta k serveru FTP `UpdateURL` na adresu URL webu.|  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.Build.Tasks.GenerateBootstrapper>   
 <xref:Microsoft.Build.Tasks.GenerateApplicationManifest>   
 <xref:Microsoft.Build.Tasks.GenerateDeploymentManifest>   
 [ClickOnce – zabezpečení a nasazení](../deployment/clickonce-security-and-deployment.md)   
 [Návod: Ruční nasazení aplikace ClickOnce](../deployment/walkthrough-manually-deploying-a-clickonce-application.md)