---
title: 'Krok 9: Vyzkoušejte další funkce | Dokumentace Microsoftu'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
ms.assetid: 1b0c5c80-e5a6-4f69-a4a4-0e89a82d4de0
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 495d98f4061c258c78b2b74929428aec4eb3ec0c
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65678940"
---
# <a name="step-9-try-other-features"></a>Krok 9: Vyzkoušení dalších funkcí
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Chcete-li získat další informace, zkuste změnit ikony a barvy, přidat časovač hry a zvuky. Chcete-li, aby hra byla náročnější, zkuste zvětšit hrací plochu a upravte časovač.  
  
 Chcete-li stáhnout úplnou verzi vzorku, přečtěte si téma [ukázkový kurz pro dokončení Porovnávací hra](http://code.msdn.microsoft.com/Complete-Matching-Game-4cffddba).  
  
### <a name="to-try-other-features"></a>Vyzkoušení dalších funkcí  
  
- Nahraďte ikony a barvy těmi, které zvolíte.  
  
    > [!TIP]
    > Podívejte se na popisku [Forecolor](https://msdn.microsoft.com/library/system.windows.forms.control.forecolor%28v=vs.110%29.aspx) vlastnost.  
  
- Přidejte časovač hry, který sleduje, jak dlouho hráči trvá, než vyhraje.  
  
    > [!TIP]
    > K tomu můžete přidat popisek, který ve formuláři nad kontejnerem TableLayoutPanel zobrazí uplynulý čas, a do formuláře přidat další časovač pro sledování času. Použijte kód ke spuštění časovače, když hráč zahájí hru, a zastavení časovače, jakmile hráč spojí poslední dvě ikony.  
  
- Pokud hráč najde shodu, přidejte zvuk, jiný zvuk, když hráč odkryje dvě ikony, které neodpovídají, a třetí zvuk, když program znovu skryje ikony.  
  
    > [!TIP]
    > Chcete-li přehrát zvuky, můžete použít obor názvů System.media. Zobrazit [Play Sounds in Windows Forms App (C# .NET)](http://youtu.be/qOh4ooHg1UU) nebo [jak pro přehrávání Audio In Visual Basic](http://youtu.be/-4oPDeQrtMs) Další informace.  
  
- Udělejte hru obtížnější tím, že zvětšíte hrací plochu.  
  
    > [!TIP]
    > Bude potřeba udělat více než jen přidat řádky a sloupce do kontejneru TableLayoutPanel – bude také nutné zvážit počet ikon, které vytvoříte.  
  
- Udělejte hru náročnější tím, že skryjete první ikonu, pokud je hráč příliš pomalý a nezvolí druhou ikonu do vypršení určitého časového limitu.  
  
### <a name="to-continue-or-review"></a>Chcete-li pokračovat nebo přezkoumat  
  
- Pokud si nevíte rady nebo máte otázky k programování, můžete zveřejnit svůj dotaz na jednom z diskuzních fór MSDN. Zobrazit [fórum Visual Basic](http://social.msdn.microsoft.com/Forums/home?forum=vbgeneral) a [fórum Visual C#](http://social.msdn.microsoft.com/Forums/home?forum=csharpgeneral).  
  
- K dispozici jsou užitečné bezplatné video výukové materiály. Další informace o programování v jazyce Visual Basic najdete v tématu [základy jazyka Visual Basic: Vývoj pro naprosté začátečníky](http://channel9.msdn.com/Series/Visual-Basic-Development-for-Absolute-Beginners). Další informace o programování v jazyce Visual C#, naleznete v tématu [ C# základní informace: Vývoj pro naprosté začátečníky](http://channel9.msdn.com/Series/C-Sharp-Fundamentals-Development-for-Absolute-Beginners).  
  
- Chcete-li vrátit k předchozímu kroku tutoriálu, přečtěte si téma [krok 8: Přidejte metodu k ověření, zda hráč zvítězil](../ide/step-8-add-a-method-to-verify-whether-the-player-won.md).
