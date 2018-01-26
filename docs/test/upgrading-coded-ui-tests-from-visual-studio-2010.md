---
title: "Upgrade programových testů UI z produktu Visual Studio 2010 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: 1af9c5634770b08b7903033226f44630bdb0e133
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="upgrading-coded-ui-tests-from-visual-studio-2010"></a>Upgrade programových testů UI z produktu Visual Studio 2010
Testování projektů obsahující programové testy uživatelského rozhraní, které byly vytvořeny v [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] SP1 jsou bezobslužně opravit při otevření v sadě Visual Studio 2012 nebo novější. Pokud projektů testů jsou zaškrtnutá políčka do správy zdrojového kódu, soubory projektu jsou rezervovány pro tato oprava. Jakmile opravit, tyto testovací projekty obsahující programové může testů uživatelského rozhraní, potom použít v obou [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] SP1 a [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].  
  
 **Požadavky**  
  
-   Visual Studio Enterprise  
  
> [!NOTE]
> Visual Studio obsahuje více než jeden typ projekt test. Pokud vytvoříte nový programového testu uživatelského rozhraní, budou vytvořeny v typu projektu programových testů uživatelského rozhraní.
  
> [!WARNING]
>  [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)]projektů testů, které obsahují programové testy uživatelského rozhraní musí být znovu sestavit při otevření k testovacímu projektu v [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] nebo [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] -souběžného s [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].  
  
> [!WARNING]
>  Když testovacího projektu, který byl vytvořen v [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] a obsahuje jenom testy jednotek je otevřen v [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], programových testů uživatelského rozhraní nelze přidat k němu. Podobně programového testu uživatelského rozhraní nelze přidat do projektu testů jednotek, který byl vytvořen v [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].  
  
## <a name="compatibility-issues-between-visual-studio-2010-and-visual-studio-2012-or-later"></a>Problémy s kompatibilitou mezi Visual Studio 2010 a Visual Studio 2012 nebo novější  
 Následující tabulka uvádí problémy znát při migraci programové testy uživatelského rozhraní mezi [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] a [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].  
  
> [!CAUTION]
>  Je známý problém týkající se odkazů v projektech pro programových testů uživatelského rozhraní nejsou uvedena v Průzkumníku řešení. Další informace najdete v tématu zahrnuty v souboru ReadMe [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] instalačního média.  
  
|Programové funkce uživatelského rozhraní|Problém|Řešení|  
|----------------------------|-----------|--------------|  
|Testování uživatelského rozhraní Silverlight není podporována v[!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]|**Sestavení se nezdaří.**<br /><br /> Pokud máte [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] funkce aktualizací Service Pack 2 a jste vytvořili programového projektů testování uživatelského rozhraní pro aplikace Silverlight, tyto projekty nelze otevřít v [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].|Doporučujeme, která můžete spravovat tyto projekty v [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] pouze funkce aktualizací Service Pack 2.|  
|Testování uživatelského rozhraní Firefox není podporována v[!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]|**Sestavení bude úspěšné, spusťte test se nezdaří**<br /><br /> Pokud máte [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] funkce aktualizací Service Pack 2 a jste vytvořili programového projektů testování uživatelského rozhraní pro webové aplikace v Firefox, tyto projekty nelze otevřít v [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].|Doporučujeme, která můžete spravovat tyto projekty v [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] pouze funkce aktualizací Service Pack 2.|  
|Nový kód uživatelského rozhraní API testování byly přidány v[!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]|**Sestavení se nezdaří.**<br /><br /> Pokud vytvoříte programových testů uživatelského rozhraní pomocí nového uživatelského rozhraní testování rozhraní API v [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], tyto projekty nelze otevřít v [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)].|Projektů pomocí nového rozhraní API se mají spravovat v [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] pouze.|  
|V [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)], uvnitř příkazu 'Zvolte' v souboru csproj byly přidány odkazy. V [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], zahrnout odkazy na programového sestavení testu uživatelského rozhraní používáme soubor cíle zpětnou vazbu.|V [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], programového testu uživatelského rozhraní nelze přidat do testovacího projektu vytvořené v [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] (nebo s aktualizací SP1), neobsahoval programového testu uživatelského rozhraní.<br /><br /> Proces opravy přidá soubor cíle a vyberte příkaz. Pokud programového testu uživatelského rozhraní není k testovacímu projektu, pak projekt je označena jako opravit a odkazy na příslušné se nepřidají při přidávání programového testu uživatelského rozhraní v [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].|Budete muset vytvořit nový projekt testů ve stejném řešení pomocí [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] a přidejte svůj nový Test programového uživatelského rozhraní v ní. Alternativně můžete přidat programových testů uživatelského rozhraní do testovacího projektu v [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] SP1 a otevřete který projektu v [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].|  
  
##  <a name="UpgradingCodedUIFromVS2010_Update"></a> Visual Studio 2010 SP1 Update  
 Aktualizace [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] SP1 s podporou kompatibility pro sadu Visual Studio 2012 nebo novější a Windows 8 nebo novější, je k dispozici ke stažení na [Microsoft Download Center](http://www.microsoft.com/download/details.aspx?id=34677) a aktualizovat také jako Visual Studio.  
  
 Po instalaci aktualizace, následující [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] SP1 pro systém Windows 8 se zlepší programových funkcí nástroj test uživatelského rozhraní:  
  
-   Programového testu uživatelského rozhraní pro ovládací prvky založené na rozhraní .NET Framework 4.5 Windows Presentation Foundation (WPF) společnosti Microsoft můžete spustit na počítači se systémem Windows 8.  
  
-   Test programového uživatelského rozhraní pro 64bitovou (x 64) Internet Explorer 10 můžete spustit na počítači se systémem Windows 8.  
  
 Aktualizace také obsahuje opravy pro následující problémy:  
  
-   **Pokrytí kódu:** nemůže otevřít soubor pokrytí kódu (.coverage), který je vytvořen pomocí sady Visual Studio 2012 v [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] SP1.  
  
-   **Bezvýchodná situace testovacích artefaktů:** má váš tým artefaktu test, který je přiřazen k neplatný uživatel v Team Foundation Server (TFS) 2010. Například uživatel opustil společnost, ale stále má testovacího případu mu přiřazený. Upgradujete na TFS 2012 sady TFS 2010. Používáte [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)] 2010 tak, aby připojení k serveru upgradované sady TFS. Nemůžete přiřadit artefaktů testu pro všechny uživatele TFS pomocí [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)] 2010.  
  
-   **Zátěžové testování:** při spuštění zátěžového testu společně s typem sítě než profil místní sítě (LAN) v počítači to se systémem Windows 8, ovladači sítě emulátoru způsobuje chybu operačního systému. Další podrobnosti najdete v tématu [2736182 článku KB](http://support.microsoft.com/kb/2736182).  
  
## <a name="see-also"></a>Viz také

[Přenosy, migrace a upgrade projektů sady Visual Studio](../porting/port-migrate-and-upgrade-visual-studio-projects.md)  
[Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)  
[Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
