---
title: Řešení potíží s nasazením řešení Office
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- ClickOnce deployment [Office development in Visual Studio], troubleshooting
- Office development in Visual Studio, troubleshooting
- deploying applications [Office development in Visual Studio], troubleshooting
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 854264da676ec52d93030371213fa3d8d57eb69f
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/04/2018
ms.locfileid: "34693205"
---
# <a name="troubleshoot-office-solution-deployment"></a>Řešení potíží s nasazením řešení Office
  Toto téma obsahuje informace o tom, jak vyřešit nejčastější problémy, které se můžete setkat při nasazení řešení pro systém Office.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## <a name="troubleshoot-office-solutions-by-using-the-event-viewer"></a>Řešení potíží řešení pro systém Office pomocí prohlížeče událostí  
 Můžete v prohlížeči událostí v systému Windows naleznete v chybových zprávách, které jsou zachyceny [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] při instalaci nebo odinstalaci řešení Office. Tyto zprávy z protokoly událostí můžete použít k vyřešení instalace a nasazení problémy. Další informace najdete v tématu [protokolování událostí pro řešení pro systém Office](../vsto/event-logging-for-office-solutions.md).  
  
## <a name="change-the-assembly-name-causes-conflicts"></a>Změňte název sestavení způsobí, že je v konfliktu  
 Pokud změníte **název sestavení** hodnotu **aplikace** stránky **Návrhář projektu** poté, co již nasadíte řešení, nástroje pro publikování upraví Instalační balíček tak, aby měl jeden *Setup.exe* soubor a dvě manifesty nasazení. Pokud nasadíte dva soubory manifestu, může dojít k následující podmínky:  
  
-   Pokud koncový uživatel nainstaluje obě verze, aplikace načte obou doplňků VSTO.  
  
-   Pokud doplňku VSTO byla nainstalována před název sestavení změnil, koncový uživatel nikdy získávat aktualizace.  
  
 Nechcete-li tyto podmínky, Neměnit na řešení **název sestavení** hodnotu po nasazení řešení.  
  
## <a name="check-for-updates-takes-a-long-time"></a>Zkontrolujte aktualizace trvá dlouhou dobu  
 Visual Studio 2010 Tools for Office runtime poskytuje položku registru, která mohou správci nastavit hodnotu časového limitu pro stahování manifesty a řešení.  
  
#### <a name="to-set-the-time-out-value"></a>Chcete-li nastavit hodnotu časového limitu  
  
1.  V registru přejděte do následujícího klíče:  
  
     **HKEY_CURRENT_USER\Software\Microsoft\VSTA**  
  
2.  V **AddInTimeout** podklíčů, nastavit hodnotu časového limitu v milisekundách.  
  
     Pokud **AddInTimeout** podklíč neexistuje, vytvořte ho typu DWORD.  
  
## <a name="cant-update-or-publish-to-a-network-file-share"></a>Nelze aktualizovat nebo publikovat do síťové sdílené složky  
 Řešení Office, které jsou v síťové sdílené složky může zobrazit zprávu zavádějící během aktualizace, pokud na řešení *Setup.exe* soubor uzamčen v procesu aktualizace je publikován. Říci, následující zpráva: "nelze přidat 'setup.exe, na web. Soubor setup.exe již existuje na tomto webu."  
  
 Aby se zabránilo se zamykáním souborů, můžete nastavit sdílené složky jen pro čtení pro koncové uživatele. Ale pokud dokumenty ve sdílené složce, budou také bude koncovým uživatelům jen pro čtení.  
  
## <a name="prerequisites-for-microsoft-office-arent-installed"></a>Nejsou nainstalované součásti požadované pro Microsoft Office  
 Rozhraní .NET Framework, můžete přidat [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]a primární spolupracující sestavení Office na instalační balíček jako požadované součásti, které jsou nasazeny s vaším řešením Office. Informace o tom, jak nainstalovat primární spolupracující sestavení najdete v tématu [konfigurace počítače pro vývoj řešení pro systém Office](../vsto/configuring-a-computer-to-develop-office-solutions.md) a [postup: Primární spolupracující sestavení Office nainstalovat](../vsto/how-to-install-office-primary-interop-assemblies.md).  
  
## <a name="publish-using-localhost-can-cause-installation-problems"></a>Publikovat pomocí "Localhost" může způsobit problémy s instalací  
 Při použití "http://localhost" jako umístění instalace nebo publikování pro řešení na úrovni dokumentu, **Průvodci publikováním** není převést řetězec na název skutečné počítače. Řešení v takovém případě musí být nainstalována na vývojovém počítači. Chcete-li nasazené řešení, které používají službu IIS na vývojovém počítači, použijte plně kvalifikovaný název pro všechna umístění HTTP/HTTPS nebo FTP místo localhost.  
  
## <a name="cached-assemblies-are-loaded-instead-of-updated-assemblies"></a>Načíst místo aktualizované sestavení jsou uložené v mezipaměti sestavení  
 Fusion, zavaděč sestavení rozhraní .NET Framework a načte kopii sestavení v mezipaměti, když výstupní cesta k projektu je v síťové sdílené složky, je podepsaný sestavení se silným názvem a verze sestavení přizpůsobení nemění. Pokud aktualizujete sestavení, které splňuje tyto podmínky, aktualizace se nezobrazí při příštím spuštění projektu, protože je načtena kopie uložené v mezipaměti.  
  
 Visual Studio můžete nakonfigurovat tak, aby Fusion budou stahovat sestavení při každém spuštění projektu.  
  
### <a name="to-download-assemblies-instead-of-loading-cached-copies"></a>Chcete-li stáhnout sestavení místo načítání kopie v mezipaměti  
  
1.  Na řádku nabídek zvolte **projektu**, * ProjectName ***vlastnosti**.  
  
2.  Na **aplikace** vyberte **informací o sestavení**.  
  
3.  V prvním **verze sestavení** pole, zadejte hvězdičku (\*) a potom zvolte **OK** tlačítko.  
  
 Po změně verze sestavení, můžete nadále podepsat své sestavení se silným názvem a Fusion načte nejnovější verzi vlastního nastavení.  
  
## <a name="installation-fails-when-the-uri-has-characters-that-arent-us-ascii"></a>Instalace selže, pokud identifikátor URI obsahuje znaky, které nejsou US-ASCII  
 Když publikujete řešení Office na umístění HTTP/HTTPS nebo FTP, složka nemůže mít libovolné znaky Unicode, které nejsou v US-ASCII. Takové znaků může způsobit nekonzistentní chování v instalačním programu. Pro cestu instalace použijte znaků US-ASCII.  
  
## <a name="prompt-to-manually-uninstall-appears-when-you-publish-and-install-a-solution-on-the-development-computer"></a>Při publikování a instalaci řešení na vývojovém počítači, zobrazí se výzva k ruční odinstalaci  
 Při sestavování řešení Office na integrovaný verzi se automaticky registruje. Pokud jste dříve publikované a nainstalovat do stejného řešení na vývojovém počítači, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] zjistí, že cesta instalace pro integrované a publikovaná verze se liší, jakmile řešení je vedle vytvořen, znovu sestavit nebo publikovaná. Chybová zpráva říká "přizpůsobení nelze nainstalovat, protože je aktuálně nainstalována jiná verze a z tohoto umístění nelze upgradovat." Klíče registru se aktualizuje vždy, když je znovu sestavit řešení. Před publikování, ladění a spouštějí novou verzi, tedy musí odinstalovat předchozí verzi.  
  
 Chcete-li zabránit zobrazování zprávy, vytvořte jiného uživatelského účtu ve svém vývojovém počítači nasazení otestovat. Jako alternativu můžete odinstalovat verze ze seznamu nainstalovaných programů v počítači před dalším publikování, ladění nebo znovu sestavte řešení.  
  
## <a name="uncaught-exception-or-method-not-found-error-when-you-install-a-solution"></a>Nezachycenou výjimku nebo metoda chyby při instalaci řešení nebyla nalezena  
 Když instalujete otevřením manifest nasazení řešení Office ( *.vsto* soubor), se může objevit Office aplikace, dokumentu nebo sešitu chybové zprávy pro následující podmínky:  
  
-   Metoda nebyla nalezena.  
  
-   MissingMethodException.  
  
-   Nezachycená výjimka.  
  
 Chcete-li tyto chybové zprávy, nainstalujte spuštěním instalačního programu řešení.  
  
 Při instalaci řešení bez spuštění instalačního programu, instalační program nemá vyhledávat nebo instalace požadovaných součástí. Instalační program kontroluje správnou verzi požadavky a nainstaluje je podle potřeby.  
  
## <a name="manifest-registry-keys-for-add-ins-change-after-an-installshield-limited-edition-project-is-built"></a>Manifest klíče registru pro doplňky změnu po projektu InstallShield Limited Edition  
 Klíč registru manifestu, který je součástí instalace doplňku VSTO programu někdy změny z *.vsto* k *. dll.manifest* při sestavení projektu InstallShield Limited Edition.  
  
 Chcete-li tento problém obejít, vytvoření projektu InstallShield Limited Edition v jiné řešení nebo použijte CompanyName.AddinName jako hodnotu klíče registru, který obsahuje název doplňku VSTO.  
  
## <a name="the-clickonce-installer-for-your-office-solution-doesnt-install-the-primary-interop-assemblies"></a>Instalační program ClickOnce pro řešení Office neinstaluje primární spolupracující sestavení  
 Když spustíte instalační program, který vytváří ClickOnce pro řešení Office, instalační program pro primární spolupracující sestavení sady Office (PIA) spustí jenom v případě, že žádné PIA jsou již nainstalovány.  
  
 Instalační program není správně nainstalováno PIA, nainstalujte je ručně spuštěním instalačního souboru, který je pojmenován *o2007pia.msi* z instalačního adresáře.  
  
## <a name="reinstall-office-solutions-causes-an-argument-out-of-range-exception"></a>Přeinstalujte Office řešení příčiny argument výjimka mimo rozsah  
 Při přeinstalaci řešení Office, <xref:System.ArgumentOutOfRangeException> výjimka může zobrazují se následující chybová zpráva: Zadaný argument je mimo rozsah platných hodnot.  
  
 K této situaci dochází v případě velká a malá písmena pro adresu URL pro umístění instalace je odlišná. Tato chyba by například zobrazit, pokud jste nainstalovali řešení Office z [ http://fabrikam.com/ExcelSolution.vsto ](http://fabrikam.com/ExcelSolution.vsto) poprvé a pak se použije [ http://fabrikam.com/excelsolution.vsto ](http://fabrikam.com/excelsolution.vsto) druhém.  
  
 Chcete-li zabránit zobrazování zprávy, používejte při instalaci řešení pro systém Office stejné malá a velká písmena.  
  
## <a name="cant-install-a-clickonce-solution-by-opening-the-deployment-manifest-from-the-web"></a>Nelze nainstalovat řešení ClickOnce otevřením manifest nasazení z webu  
 Uživatelé můžou nainstalovat řešení pro systém Office tak, že otevřete manifest nasazení z webu. Ale některé instalace bloky Internetové informační služby (IIS) *.vsto* příponou názvu souboru. Předtím, než ho použijete k nasazení řešení Office, je nutné zadat typ MIME ve službě IIS.  
  
 Informace o tom, jak definovat typ MIME ve službě IIS 6 najdete v tématu [konfigurovat typy MIME (IIS 6.0)](http://www.microsoft.com/technet/prodtechnol/WindowsServer2003/Library/IIS/cd72c0dc-c5b8-42e4-96c2-b3c656f99ead.mspx?mfr=true).  
  
 Informace o tom, jak definovat typ MIME ve službě IIS 7 najdete v tématu [přidat typ MIME (IIS7)](http://technet.microsoft.com/library/cc725608(WS.10).aspx).  
  
 Nastavit rozšíření na **.vsto** a zda má typ MIME **application/x-ms-vsto**.  
  
## <a name="see-also"></a>Viz také:  
 [Řešení potíží s nasazením ClickOnce](/visualstudio/deployment/troubleshooting-clickonce-deployments)   
 [Nasazení řešení Office](../vsto/deploying-an-office-solution.md)  
  
  