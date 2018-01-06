---
title: "Krok 9: Vyzkoušejte jiné funkce | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1b0c5c80-e5a6-4f69-a4a4-0e89a82d4de0
caps.latest.revision: "11"
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 5db8c070b5e0796e64071a8c28d4d36715cd8fc0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="step-9-try-other-features"></a>Krok 9: Vyzkoušejte jiné funkce
Chcete-li získat další informace, zkuste změnit ikony a barvy, přidat časovač hry a zvuky. Chcete-li, aby hra byla náročnější, zkuste zvětšit hrací plochu a upravte časovač.  
  
 Si můžete stáhnout dokončené verzi příkladu [kurz ukázka dokončení odpovídající hra](http://code.msdn.microsoft.com/Complete-Matching-Game-4cffddba).  
  
### <a name="to-try-other-features"></a>Vyzkoušení dalších funkcí  
  
-   Nahraďte ikony a barvy těmi, které zvolíte.  
  
    > [!TIP]
    >  Podívejte se na jmenovky [Forecolor](http://msdn.microsoft.com/library/system.windows.forms.control.forecolor.aspx) vlastnost.  
  
-   Přidejte časovač hry, který sleduje, jak dlouho hráči trvá, než vyhraje.  
  
    > [!TIP]
    >  K tomu můžete přidat popisek, který ve formuláři nad kontejnerem TableLayoutPanel zobrazí uplynulý čas, a do formuláře přidat další časovač pro sledování času. Použijte kód ke spuštění časovače, když hráč zahájí hru, a zastavení časovače, jakmile hráč spojí poslední dvě ikony.  
  
-   Pokud hráč najde shodu, přidejte zvuk, jiný zvuk, když hráč odkryje dvě ikony, které neodpovídají, a třetí zvuk, když program znovu skryje ikony.  
  
    > [!TIP]
    >  Chcete-li přehrát zvuky, můžete použít obor názvů System.media. V tématu [přehrání zvuků v aplikaci Windows Forms (C# .NET)](http://youtu.be/qOh4ooHg1UU) nebo [jak k přehrávání zvuku v jazyce Visual Basic](http://youtu.be/-4oPDeQrtMs) Další informace.  
  
-   Udělejte hru obtížnější tím, že zvětšíte hrací plochu.  
  
    > [!TIP]
    >  Budete potřebovat více než jen přidání řádků a sloupců do TableLayoutPanel - také musíte vzít v úvahu počet ikony, které vytvoříte.  
  
-   Udělejte hru náročnější tím, že skryjete první ikonu, pokud je hráč příliš pomalý a nezvolí druhou ikonu do vypršení určitého časového limitu.  
  
### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  
  
-   Pokud si nevíte rady nebo máte otázky k programování, můžete zveřejnit svůj dotaz na jednom z diskuzních fór MSDN. V tématu [jazyka Visual Basic fórum](http://social.msdn.microsoft.com/Forums/home?forum=vbgeneral) a [Visual C# fórum](http://social.msdn.microsoft.com/Forums/home?forum=csharpgeneral).  
  
-   K dispozici jsou užitečné bezplatné video výukové materiály. Další informace o programování v jazyce Visual Basic, najdete v části [základy jazyka Visual Basic: vývoj pro začátečníky absolutní](http://channel9.msdn.com/Series/Visual-Basic-Development-for-Absolute-Beginners). Další informace o programování v jazyce Visual C#, najdete v části [Základy C#: vývoj pro začátečníky absolutní](http://channel9.msdn.com/Series/C-Sharp-Fundamentals-Development-for-Absolute-Beginners).  
  
-   Chcete-li vrátit k předchozímu kroku kurzu, přečtěte si téma [krok 8: Přidejte metodu k ověřte, zda hráč vyhrál](../ide/step-8-add-a-method-to-verify-whether-the-player-won.md).