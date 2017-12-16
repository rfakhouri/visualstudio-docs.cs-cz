---
title: "Implementace vlastních zásad analýzy kódu vrácení se změnami pro spravovaný kód | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.code.analysis.selecttfsrulesets
- vs.code.analysis.browsefortfsruleset
- vs.code.analysis.policyeditor
ms.assetid: fd029003-5671-4b24-8b6f-032e0a98b2e8
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3d8747ddb78c257ae0ba38d24fb2c5cc529f67b9
ms.sourcegitcommit: f0ddee934713ea9126fa107018a57a94a05eafd3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/12/2017
---
# <a name="implementing-custom-code-analysis-check-in-policies-for-managed-code"></a>Implementace vlastních zásad vrácení se změnami Analýzy kódu pro spravovaný kód
Analýza kódu, že zásad vrácení se změnami určuje sadu pravidel, která členy týmového projektu musíte spustit na zdrojový kód, než se změnami do správy verzí. Společnost Microsoft poskytuje sadu standard *sad pravidel* pravidel analýzy kódu této skupiny do funkční oblastí. *Sady pravidel vlastních zásad vrácení se změnami* zadejte sadu pravidel analýzy kódu, které jsou specifické pro týmový projekt. Sada pravidel je uložené v souboru analýza.  
  
 Nastavit na úrovni týmového projektu a určeného umístění souboru analýza ve stromu řízení verze zásad vrácení se změnami. Neexistují žádná omezení umístění ovládacího prvku verzi sady team zásady vlastní pravidlo.  
  
 Analýza kódu je nakonfigurován pro projekty jednotlivých kódu v okně Vlastnosti pro každý projekt. Vlastní sadu pravidel pro projekt kódu je určena fyzické umístění souboru analýza v místním počítači. Pokud soubor analýza zadán, který je umístěný na stejné jednotce jako projektu kódu, Visual Studio použije relativní cesta k souboru v konfiguraci projektu.  
  
 Navrhované postup pro vytvoření týmového projektu vlastní sady pravidel je uložit soubor Analýza zásad vrácení se změnami ve speciální složky, která není součástí žádného kód projektu. Pokud soubor uchováváte v vyhrazené složky, můžete použít oprávnění, která omezují, kteří mohou upravovat soubor pravidel a můžou snadno přesunout adresářovou strukturu obsahující projekt do jiného adresáře nebo počítače.  
  
## <a name="creating-the-team-project-custom-check-in-rule-set"></a>Vytváření vlastní pravidlo vrácení se změnami sadu Team projektu  
 Pokud chcete vytvořit vlastní sadu pravidel pro týmový projekt, nejprve vytvořit speciální složky pro pravidlo zásad vrácení se změnami nastavené v **Průzkumník správy zdrojového kódu**. Potom můžete vytvořit soubor sady pravidel a přidání souboru do správy verzí. Nakonec zadejte sady analysis zásady kódu, vrácení se změnami pro týmový projekt pravidel.  
  
> [!NOTE]
>  Vytvořit složku v týmového projektu, je nejprve nutné mapovat kořenového týmového projektu do umístění v místním počítači.  
  
#### <a name="to-create-the-version-control-folder-for-the-check-in-policy-rule-set"></a>Vytvoření složky řízení verze pro sadu pravidel zásad vrácení se změnami  
  
1.  V [!INCLUDE[esprtfc](../code-quality/includes/esprtfc_md.md)], rozbalte uzel týmového projektu a pak klikněte na tlačítko **správy zdrojového kódu**.  
  
2.  V **složky** podokně klikněte pravým tlačítkem na týmový projekt a potom klikněte na **novou složku**.  
  
3.  V hlavním podokně Správa zdrojového kódu, klikněte pravým tlačítkem na **novou složku**, klikněte na tlačítko **přejmenovat**a zadejte název složky sady pravidel.  
  
#### <a name="to-create-the-check-in-policy-rule-set"></a>Chcete-li vytvořit sadu pravidel zásad vrácení se změnami  
  
1.  Na **soubor** nabídky, přejděte na příkaz **nový**a potom klikněte na **soubor**.  
  
2.  V **kategorie** seznamu, klikněte na tlačítko **Obecné**.  
  
3.  V **šablony** klikněte dvakrát **sady pravidel analýzy kódu**.  
  
4.  Zadejte pravidla, která zahrnují v sadě pravidel a poté uložte soubor sady pravidlo ke složce sadu pravidel, který jste vytvořili.  
  
     Další informace najdete v tématu [vytváření vlastní sady pravidel](../code-quality/creating-custom-code-analysis-rule-sets.md)  
  
#### <a name="to-add-the-rule-set-file-to-version-control"></a>Chcete-li přidat pravidlo nastavte souboru do správy verzí  
  
1.  V **Průzkumník správy zdrojového kódu**, klikněte pravým tlačítkem na novou složku a pak klikněte na tlačítko **přidat položky do složky**.  
  
     Další informace najdete v tématu [Git a služby VSTS](/vsts/git/overview).  
  
2.  Kliknutím pravidlo nastavené soubor, který jste vytvořili a pak klikněte na **Dokončit**.  
  
     Soubor je přidán do správy zdrojového kódu a vyhrazený pro vás.  
  
3.  V **Průzkumník správy zdrojového kódu** okno podrobností, klikněte pravým tlačítkem na název souboru a pak klikněte na **změnami čekající změny**.  
  
4.  V **vrácení se změnami** dialogové okno, máte možnost přidat komentář, a potom klikněte na **změnami**.  
  
    > [!NOTE]
    >  Pokud jste již nakonfigurovali zásady pro analýzu kódu vrácení se změnami pro týmový projekt a máte vybraný **vynutit vrácení se změnami tak, aby obsahovala pouze soubory, které jsou součástí aktuální řešení**, se aktivují upozornění selhání zásad. V dialogovém okně zásadu selhání vyberte **selhání zásady přepsat a pokračovat vrácení se změnami**. Přidejte požadované komentář a potom klikněte na **OK**.  
  
#### <a name="to-specify-the-rule-set-file-as-the-check-in-policy"></a>Chcete-li určit pravidla nastavit soubor jako zásad vrácení se změnami  
  
1.  Na **Team** nabídky, přejděte na příkaz **nastavení týmového projektu**a potom klikněte na **správy zdrojového kódu**.  
  
2.  Klikněte na tlačítko **zásad vrácení se změnami**a potom klikněte na **přidat**.  
  
3.  V **zásad vrácení se změnami** klikněte dvakrát **analýza kódu**a ujistěte se, že **vynutit analýzy kódu pro spravovaný kód** je zaškrtnuté políčko.  
  
4.  V **spuštění této sady pravidel** seznamu, klikněte na tlačítko  **\<vyberte pravidlo nastavené od správy zdrojového kódu >**.  
  
5.  Zadejte cestu k souboru sady pravidel zásad vrácení se změnami ve správě verzí.  
  
     Cesta musí splňovat následující syntaxi:  
  
     **$/** `TeamProjectName` **/** `VersionControlPath`  
  
    > [!NOTE]
    >  Cestu můžete zkopírovat pomocí jedné z následujících postupů v **Průzkumník správy zdrojového kódu**:  
  
    -   V **složky** podokně klikněte na složku, která obsahuje soubor sady pravidel. Zkopírujte cesta ovládacích prvků verze složky, která se zobrazí v **zdroj** a ručně zadejte název souboru sady pravidel.  
  
    -   V okně podrobností klikněte pravým tlačítkem na soubor sady pravidlo a pak klikněte na **vlastnosti**. Na **Obecné** kartě, zkopírujte hodnotu v **název serveru**.  
  
## <a name="synchronizing-code-projects-to-the-check-in-policy-rule-set"></a>Synchronizace projektů kód pro sadu pravidel zásad vrácení se změnami  
 Zadáte nastavit pravidlo zásad vrácení se změnami týmového projektu, jako je sada pravidel analýzy kódu pro konfigurace projektu kódu v dialogovém okně Vlastnosti projektu kódu. Pokud je sada pravidel se nachází na stejné jednotce jako projektu kódu, je relativní cesta slouží k určení sady pravidel, pokud je vybrána složka z dialogového okna souboru. Povoluje relativní cesty nastavení vlastnosti projektu přenosný do jiných počítačů, které používají podobné místní verzi řízení struktury.  
  
#### <a name="to-specify-a-team-project-rule-set-as-the-rule-set-of-a-code-project"></a>Zadejte pravidla týmového projektu nastavit jako sady pravidel projektu kódu  
  
1.  V případě potřeby načtení zásad vrácení se změnami pravidlo sadu složku a soubor z verzí.  
  
     Můžete provést tento krok v **Průzkumník správy zdrojového kódu** kliknutím pravým tlačítkem na složku a potom kliknutím na sady pravidel **získat nejnovější verzi**.  
  
2.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt kódu a pak klikněte na tlačítko **vlastnosti**.  
  
3.  **Klikněte na tlačítko Analýza kódu**.  
  
4.  V případě potřeby klikněte na příslušné možnosti v **konfigurace** a **platformy** uvádí.  
  
5.  Chcete-li spuštění analýzy kódu pokaždé, když projektu kódu se sestavuje pomocí Zadaná konfigurace, vyberte **povolit analýza kódu v sestavení (definuje CODE_ANALYSIS konstanta)** zaškrtávací políčko.  
  
6.  Ignorovat kódu v součásti od jiných společností, vyberte **potlačit výsledky z generovaného kódu** zaškrtávací políčko.  
  
7.  V **spuštění této sady pravidel** seznamu, klikněte na tlačítko  **\<Procházet... >**.  
  
8.  Zadejte místní verzi souboru sady pravidel zásad vrácení se změnami.