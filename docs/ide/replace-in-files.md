---
title: "Visual Studio najít a nahradit v souborech | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.findreplace.replaceinfiles
- vs.replaceinfiles
helpviewer_keywords:
- text searches, replacing text
- Find and Replace window, Replace in Files tab
- Replace in Files tab, Find and Replace window
ms.assetid: ca361466-53bd-44db-a28a-3a74bc03b028
caps.latest.revision: "29"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 8b13903fc02a716de951847ce9409e750764b123
ms.sourcegitcommit: ec1c7e7e3349d2f3a4dc027e7cfca840c029367d
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/07/2017
---
# <a name="replace-in-files"></a>Nahradit v souborech
**Nahradit v souborech** umožňuje hledat kód zadanou sadu souborů pro řetězec nebo výraz a změnit některé nebo všechny nalezených shod. Nebyla nalezena shoda a akcí provedených jsou uvedeny v **Najít výsledky** vybrán v okně **způsobit možnosti**.  
  
> [!NOTE]
> Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, například k **Obecné** nebo **Visual C++** nastavení, vyberte **nástroje**, **nastavení importu a exportu**a potom Zvolte **obnovit nastavení**.
  
K zobrazení můžete použít některou z následujících metod **nahradit v souborech** v **najít a nahradit** okno.  
  
### <a name="to-display-replace-in-files"></a>Chcete-li zobrazit nahradit v souborech  
  
1.  Na **upravit** nabídky, rozbalte položku **najít a nahradit**.  
  
2.  Zvolte **nahradit v souborech**.  
  
     – nebo –  
  
     Pokud **najít a nahradit** , je již otevřeno, na panelu nástrojů vyberte **nahradit v souborech**.  
  
## <a name="find-what"></a>Najít  
Vyhledat nový textový řetězec nebo výraz, zadejte do pole. Vyhledávat libovolné 20 řetězce, které jste hledali naposledy, otevřete seznam a vyberte text, pro který chcete vyhledávat. Zvolte sousedním **Tvůrce** tlačítko, pokud chcete použít jeden nebo více regulární výrazy v hledanému řetězci. Další informace najdete v tématu [pomocí regulárních výrazů v sadě Visual Studio](../ide/using-regular-expressions-in-visual-studio.md).
  
## <a name="replace-with"></a>Nahraďte  
Nahradit instance řetězce do **najít** pole s jiným řetězcem, zadejte náhradní řetězec v **nahradit za** pole. Odstranění instance řetězce do **najít** pole, to pole ponechat prázdné. Otevřete seznamu zobrazíte 20 řetězců, pro které jste naposledy vyhledávat. Zvolte sousedním **Tvůrce** tlačítko, pokud chcete použít jeden nebo více regulární výrazy v náhradní řetězec. Další informace najdete v tématu [pomocí regulárních výrazů v sadě Visual Studio](../ide/using-regular-expressions-in-visual-studio.md).
  
## <a name="look-in"></a>Oblast hledání  
Možnost výběru z **naleznete v** rozevíracího seznamu určuje, zda **nahradit v souborech** vyhledá pouze v aktuálně aktivních soubory nebo vyhledá všechny soubory uložené v rámci určitých složek. Vyberte ze seznamu obor vyhledávání, zadejte cestu ke složce nebo klikněte na **Procházet (...)**  tlačítko pro zobrazení **zvolte složky výsledků hledání** dialogové okno pole a zvolte skupinu složek, které chcete vyhledat. Můžete také zadat cestu přímo do **Hledat v** pole.
  
> [!NOTE]
>  Pokud **Hledat v** možnost způsobí, že jste k vyhledání souboru, který máte rezervován od správy zdrojového kódu, prohledají se jenom verze tohoto souboru, který byl stažen do místního počítače.
  
## <a name="find-options"></a>Možnosti hledání  
Můžete rozbalit nebo sbalit **najít možnosti** části. Následující možnosti může být vybrána nebo vymazána:  
  
Rozlišovat velikost písmen  
Při výběru, **výsledky hledání** windows zobrazí pouze instance **najít** řetězec, který se splní podle obsahu a podle případu. Například vyhledejte "MyObject" s **malá a velká písmena** vybrané bude vracet "MyObject", ale ne "myobject" nebo "MYOBJECT."  

Celá slova  
Při výběru, **Najít výsledky** windows zobrazí pouze instance **najít** řetězec, který se splní v celá slova. Například vyhledejte "MyObject" vrátí "MyObject", ale ne "CMyObject" nebo "MyObjectC."  

Použití regulárních výrazů  
Když toto políčko zaškrtnuto, můžete použít speciální zápisy definovat strukturu textu v **najít** nebo **nahraďte** textových polí. Seznam těchto zápisy, naleznete v části [pomocí regulárních výrazů v sadě Visual Studio](../ide/using-regular-expressions-in-visual-studio.md).  

Podívejte se na tyto typy souborů  
Tento seznam uvádí typy souborů, pokud chcete hledat v **Hledat v** adresáře. Pokud toto pole ponecháte prázdné, všechny soubory v **Hledat v** prohledávaných adresářů.  

Vyberte libovolnou položku v seznamu a zadejte předkonfigurované vyhledávací řetězec, který zjistí tyto konkrétní typy souborů.  
  
## <a name="result-options"></a>Možnosti výsledku  
Můžete rozbalit nebo sbalit **způsobit možnosti** části. Následující možnosti může být vybrána nebo vymazána:  

Najít výsledky 1 – okno  
Pokud vybraná, výsledky hledání aktuální nahradí obsah **najít 1 výsledky** okno. Toto okno se automaticky otevře a zobrazí výsledky hledání. Otevřete toto okno ručně, vyberte **ostatní okna** z **zobrazení** nabídky a zvolte **najít 1 výsledky**.  

Najít okno výsledků 2  
Pokud vybraná, výsledky hledání aktuální nahradí obsah **najít 2 výsledky** okno. Toto okno se automaticky otevře a zobrazí výsledky hledání. Otevřete toto okno ručně, vyberte **ostatní okna** z **zobrazení** nabídky a zvolte **najít 2 výsledky**.  

Zobrazit pouze názvy souborů  
Když toto políčko zaškrtnuto, zobrazí seznam úplné názvů a cest pro všechny soubory, které obsahují řetězec pro hledání výsledky hledání windows. Ale výsledky neobsahují řádek kódu, kde se zobrazí řetězec. Toto zaškrtávací políčko je dostupné pro hledání v souborech jenom.  

Nechte změněné soubory otevřené po Replace všechny  
Při výběru, otevřete všechny soubory zůstanou ve kterých náhrady byly provedeny, abyste mohli vrátit zpět nebo uložte změny. Omezení paměti může být omezen počet souborů, které může zůstat otevřené po operaci nahrazení.  

> [!CAUTION]
>  Můžete použít **vrátit zpět** pouze u souborů, které zůstávají otevřený pro úpravy. Pokud tuto možnost nevyberete, soubory, které už nebyly otevřete pro úpravy zůstanou uzavřené a ne **vrátit zpět** možnost nebude k dispozici v těchto souborů.  
  
## <a name="see-also"></a>Viz také
[Hledání a nahrazení textu](../ide/finding-and-replacing-text.md)   
[Hledání v souborech](../ide/find-in-files.md)   
[Příkazy sady Visual Studio](../ide/reference/visual-studio-commands.md)