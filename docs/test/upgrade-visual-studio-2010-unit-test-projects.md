---
title: "Upgrade projektů testů jednotek sady Visual Studio 2010 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f1502b51-d6db-4894-9fbf-4a5723e4bb1a
caps.latest.revision: "8"
ms.author: douge
manager: douge
ms.openlocfilehash: 2e3e99bfad1ebf33f23c3b38189568935d0cedee
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2017
---
# <a name="upgrade-visual-studio-2010-unit-test-projects"></a>Upgrade projektů testů jednotek sady Visual Studio 2010
[!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]zahrnuje testovacího projektu kompatibilitu s [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] projektů testování SP1. Například testování projektů, které jste vytvořili pomocí [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] SP1 dají otevřít pomocí [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] bez jakéhokoli upgradu. Váš tým tedy můžete používat i [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] SP1 a [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] pro práci s stejné testovacího projektu. Další informace najdete v tématu [upgrade testů ze sady Visual Studio 2010](http://msdn.microsoft.com/en-us/e9c8b7f6-bd72-448e-8edb-d090dcc5cf52).  
  
 [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]přináší několik změn pro testování jednotky. Tyto změny, je důležité si uvědomit, problémy s kompatibilitou mezi předchozí verze sady Visual Studio a [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]. Mezi změny testování částí, významné změny je, že [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)] obsahuje více než jeden šablony projektu test, včetně šablona projektu testů jednotek. Nové testování částí se přidají do nové šablony projektu testů jednotek. Testování částí můžou být součástí jiného nová šablona projektu testovací názvem šabloně projektu programových testů uživatelského rozhraní. Další informace o nové šablony projektu testovací najdete v tématu [upgrade testů z dřívějších verzí aplikace Visual Studio](http://msdn.microsoft.com/en-us/e9c8b7f6-bd72-448e-8edb-d090dcc5cf52). Nové projektů testování částí už zahrnují souborů nastavení testů ve výchozím nastavení. Podle s výjimkou souborů nastavení testů, zlepšuje výkon testů jednotek. Pro kompatibilitu můžete dál používat existující projekty testů, které jste vytvořili pomocí sady Visual Studio 2010. Doporučujeme však odstranit testovací soubor nastavení přidružené k testovacímu projektu z důvodů výkonu, pokud máte konkrétní potřebu souborů nastavení testů. Například je možné zachovat souborů nastavení testů v případě, že spuštění testů jednotek v distribuovaném prostředí nebo která potřebujete shromáždit určité diagnostická data. Pokud nemáte podobné požadavky pomocí šablony projektu nový test jednotky nebo programové uživatelského rozhraní testování projektu šablony, můžete ručně přidáte souborů nastavení testů k nim také.  
  
> [!NOTE]
>  Stávající jednotky testů v vaše [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] projektů testování SP1 bude fungovat bez problémů mezi [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] SP1 a [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]. Nebudou provedeny žádné změny k testovacích souborů projektu při otevření projektu sady Visual Studio 2010 testovací obsahující testů jednotek v [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], nebo naopak.  
  
> [!CAUTION]
>  Visual Studio 2010 nelze otevřít C + +/ CLI projektu tohoto cíle 11.0 sady nástrojů – tedy projektu vytvořené v sadě Visual Studio 2012 nebo novějším. Toto omezení platí pro všechny C + +/ CLI projekty, není právě C + +/ CLI projektů testování částí.  
  
> [!NOTE]
>  Můžete spustit nový testování částí pomocí vstest.console.exe z příkazového řádku. Další informace o používání vstest.console.exe najdete v tématu [možnosti příkazového řádku VSTest.Console.exe](/devops-test-docs/test/vstest-console-exe-command-line-options), nebo spusťte příkaz pomocí přepínače nápovědy: **vstest.console.exe /?**. Můžete dál spouštět existující testů jednotek pomocí MStest.exe. Další informace najdete v tématu [spuštění automatizovaných testů z příkazového řádku pomocí Mstestu](/devops-test-docs/test/run-automated-tests-from-the-command-line-using-mstest) a [MSTest.exe – možnosti příkazového řádku](/devops-test-docs/test/mstest-exe-command-line-options).  
  
 Další důležitá změna je nové Průzkumníka testů. V [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)], některé testování Windows je možné, že znáte z předchozí verze sady Visual Studio jsou zastaralé, jako je například okno Test zobrazení. Průzkumníka testů je určena pro lepší podporu vývojáři a týmům, kteří začlenit testování v jejich postupy pro vývoj softwaru částí. Další informace najdete v tématu [spouštění testů jednotek pomocí Průzkumníka testů](../test/run-unit-tests-with-test-explorer.md).  
  
## <a name="compatibility-issues-between-visual-studio-2010-sp1-and-visual-studio-2012-or-later"></a>Problémy s kompatibilitou mezi Visual Studio 2010 SP1 a Visual Studio 2012 nebo novější  
 Tady jsou některé problémy znát při migraci testování částí mezi Visual Studio 2010 SP1 a [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]:  
  
|Funkce testů jednotek|Problém|Řešení|  
|-----------------------------|-----------|--------------|  
|Seznamů testů (soubory .vsmdi) jsou zastaralé v [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].|Nebudete již moci vytvořit nové seznamů testů (.vsmdi soubory) nebo spusťte seznamů testů ze sady Visual Studio. **Tip:** kategorií testů přinášejí větší flexibilitu než test jsou uvedené funkce z dřívějších verzí sady Microsoft Visual Studio. Můžete vytvořit logické operátory s kategorií testů ke spuštění testů z více kategorií společně nebo k omezení testy, které spustíte testy, které patří do více kategorií. Kategorií testů jsou také snadno přidat tak, jak vytvořit zkušební metody a není nutné udržovat seznamů testů po vytvoření zkušební metody. S použitím kategorií testů, není nutné vrátit se změnami a rezervovat  **\<název řešení > .vsmdi** soubor, který udržuje seznamů testů. Další informace najdete v tématu [definování kategorií testů pro vaše testy skupiny](/devops-test-docs/test/defining-test-categories-to-group-your-tests).|-Aby byla zachována kompatibilita s existující projekty testu, které používají seznamů testů, jsou stále moci upravit soubory .vsmdi pomocí sady Visual Studio.<br />-I když seznamů testů migrované z nelze spustit pomocí sady Visual Studio, můžete spustit je pomocí mstest.exe z příkazového řádku. Další informace najdete v tématu [spuštění automatizovaných testů z příkazového řádku pomocí Mstestu](/devops-test-docs/test/run-automated-tests-from-the-command-line-using-mstest)<br />– Pokud jste používali seznam testů ve vaší definice sestavení, můžete ji použít. Další informace najdete v tématu [postupy: Konfigurace a spuštění naplánovaná testů po sestavení aplikace](http://msdn.microsoft.com/en-us/32acfeb1-b1aa-4afb-8cfe-cc209e6183fd) a [procesu sestavení spustit testy](http://msdn.microsoft.com/Library/d05743a1-c5cf-447e-bed9-bed3cb595e38).|  
|Privátní přístupové objekty jsou zastaralé v [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)].<br /><br /> V předchozích verzích sady Visual Studio, můžete použít Publicize zadejte interní aplikace programovací rozhraní (API) a vytvořit protějšku veřejné rozhraní API, kterou můžete volat v testy, které by naopak, volání do interní rozhraní API produktu. Generování kódu může pak použijete k vytvoření testovací zástupných procedur a generovat fragment kódu uvnitř tohoto kódu.|Nebudete již moci vytvořit privátní přístupové objekty.|<ul><li>Testovací projekty Visual Studio 2010 bude zkompilování a práci [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]. Sestavení bude obsahovat výstup upozornění.</li><li>Pokud stále potřebujete testování interní rozhraní API, máte tyto možnosti:<br /><br /> <ul><li>Použití <xref:Microsoft.VisualStudio.TestTools.UnitTesting.PrivateObject> třída jako pomůcku při přístupu k interní a privátní rozhraní API v kódu. To je nalezen v sestavení Microsoft.VisualStudio.QualityTools.UnitTestFramework.dll.</li><li>Vytvořte reflexe rozhraní, které budou moct tak, aby odrážela vypnout kód pro přístup k interní nebo privátní rozhraní API.</li><li>Pokud je kód, který se pokoušíte získat přístup k interní, může být schopni přistupovat vašeho rozhraní API pomocí <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> tak testovacího kódu může mít přístup k interní rozhraní API.</li></ul></li></ul>|  
|Odebere dopadu testu|||  
|Sdílení výsledků spuštění prostřednictvím TRX protokoly z Průzkumníka testů.||Protokoly TRX stále můžete získat z příkazového řádku i Team Build.|  
  
## <a name="see-also"></a>Viz také  
 [Portování, migrace a upgrade projektů sady Visual Studio](../porting/port-migrate-and-upgrade-visual-studio-projects.md)   
 [Testování částí kódu](../test/unit-test-your-code.md)   
 [Upgrade testů z dřívějších verzí sady Visual Studio](http://msdn.microsoft.com/en-us/e9c8b7f6-bd72-448e-8edb-d090dcc5cf52)   
 [Upgrade programových testů UI z produktu Visual Studio 2010](../test/upgrading-coded-ui-tests-from-visual-studio-2010.md)
