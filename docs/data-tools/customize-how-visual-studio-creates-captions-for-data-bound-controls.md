---
title: "Přizpůsobení, jak Visual Studio vytváří titulky pro ovládací prvky vázané na data | Microsoft Docs"
ms.custom: 
ms.date: 11/03/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Label captions, Data Sources window
- smart captions
- captions, data-bound
- Data Sources Window, label captions
ms.assetid: 6d4d15f8-4d78-42fd-af64-779ae98d62c8
caps.latest.revision: "12"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: 86f0e451fe81875868db0d6ddcd9cead790800d3
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="customize-how-visual-studio-creates-captions-for-data-bound-controls"></a>Přizpůsobení, jak Visual Studio vytváří titulky pro ovládací prvky vázané na data
Když přetáhnete položky z [okno zdroje dat](add-new-data-sources.md) do návrháře, obzvláštní pozornost stává play: názvy sloupců v záhlaví popisky jsou naformátována do více čitelných řetězců, pokud dvě nebo více slova se zjistí zřetězen dohromady. Můžete upravit způsob, ve kterém jsou tyto popisky vytvořili, a nastavení **SmartCaptionExpression**, **SmartCaptionReplacement**, a **SmartCaptionSuffix** hodnoty v **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\15.0\Data Designer** klíč registru.  
  
> [!NOTE]
> Tento klíč registru neexistuje, dokud jeho vytvoření.  
  
Inteligentní přidávání titulků řídí regulární výraz zadaný do hodnoty **SmartCaptionExpression** hodnotu. Přidávání **Data Designer** klíč registru přepíše výchozí regulární výraz, který určuje titulek popisky. Další informace o regulárních výrazech najdete v tématu [pomocí regulárních výrazů v sadě Visual Studio](../ide/using-regular-expressions-in-visual-studio.md).  
  
Následující tabulka popisuje hodnoty registru, které řídí titulek popisky.  
  
|Položky registru|Popis|  
|-------------------|-----------------|  
|**SmartCaptionExpression**|Regulární výraz tak, aby odpovídaly vašim vzorům.|  
|**SmartCaptionReplacement**|Formát, který se zobrazí všechny skupiny obsažena ve **SmartCaptionExpression**.|  
|**SmartCaptionSuffix**|Volitelný řetězec má být připojen na konec titulek.|  
  
Následující tabulka uvádí vnitřní výchozí nastavení pro tyto hodnoty registru.  
  
|Položky registru|Výchozí hodnota|Vysvětlení|  
|-------------------|-------------------|-----------------|  
|**SmartCaptionExpression**|(\\\p{Ll}) (\\\p{Lu}) &#124; _ +|Odpovídá malé písmeno a velké písmeno nebo podtržítko.|  
|**SmartCaptionReplacement**|$1 $2|$1 představuje znaky shodná v závorkách první výraz a $2 představuje znaky shodná v druhé závorkách. Pokud chcete nahrazení je na první shodu, mezeru a druhý shody.|  
|**SmartCaptionSuffix**|:|Představuje znak připojenou k vrácený řetězec. Například, pokud je titulek `Company Name`, přípona umožňuje`Company Name:`|  
  
> [!CAUTION]
> Měli byste být velmi opatrní při provádění nic v editoru registru. Před úpravou ji zálohujte registru. Pokud Editor registru používán správně, můžete způsobit vážné problémy, které mohou vyžadovat přeinstalaci operačního systému. Microsoft nezaručuje, že lze vyřešit problémy, které způsobí nesprávně pomocí Editoru registru. Editor registru používáte na vlastní nebezpečí.  
>   
>  Obsahuje pokyny pro zálohování, úpravy a obnovení registru v následujícím článku Knowledge Base: [Popis registru systému Windows](http://support.microsoft.com/default.aspx?scid=kb;en-us;256986) (http://support.microsoft.com/default.aspx?scid=kb;en-us; 256986)  
  
### <a name="to-modify-the-smart-captioning-behavior-of-the-data-sources-window"></a>Chcete-li upravit inteligentní titulků chování okna zdroje dat  
  
1.  Otevřete příkazové okno kliknutím **spustit** a potom **spustit**.  
  
2.  Typ `regedit` v **spustit** dialogové okno a klikněte na tlačítko **OK**.  
  
3.  Rozbalte **HKEY_CURRENT_USER**, **softwaru*, **Microsoft**, **Visual Studio** uzlu.  
  
7.  Klikněte pravým tlačítkem myši **15.0** uzel a vytvořte novou **klíč** s názvem `Data Designers`.  
  
8.  Klikněte pravým tlačítkem myši **Data Designer** uzel a vytvořte tři nové hodnoty řetězce:

    - `SmartCaptionExpression`
    - `SmartCaptionReplacement`
    - `SmartCaptionSuffix`
  
11. Klikněte pravým tlačítkem myši **SmartCaptionExpression** hodnotu a vyberte **upravit**.  
  
12. Zadejte regulární výraz, který chcete **zdroje dat** okna.  
  
13. Klikněte pravým tlačítkem myši **SmartCaptionReplacement** hodnotu a vyberte **upravit**.  
  
14. Zadejte nahrazení řetězec formátu způsob, jakým chcete zobrazit vzory shodná v regulárním výrazu.  
  
15. Klikněte pravým tlačítkem myši **SmartCaptionSuffix** hodnotu a vyberte **upravit**.  
  
16. Zadejte znaky, které se má zobrazit na konci titulek.  
  
    Při příštím přetáhnete položky z **zdroje dat** okně titulek popisky jsou vytvořené pomocí nové hodnoty registru zadané.  
  
### <a name="to-turn-off-the-smart-captioning-feature"></a>Chcete-li vypnout funkci inteligentního titulků  
  
1.  Otevřete příkazové okno kliknutím **spustit** a potom **spustit**.  
  
2.  Typ `regedit` v **spustit** dialogové okno a klikněte na tlačítko **OK**.  
  
3.  Rozbalte **HKEY_CURRENT_USER**, **softwaru**, **Microsoft**, **Visual Studio** uzlu.  
  
7.  Klikněte pravým tlačítkem myši **15.0** uzel a vytvořte novou **klíč** s názvem `Data Designers`.  
  
8.  Klikněte pravým tlačítkem myši **Data Designer** uzel a vytvořte tři nové hodnoty řetězce:

    - `SmartCaptionExpression`
    - `SmartCaptionReplacement`
    - `SmartCaptionSuffix`
  
11. Klikněte pravým tlačítkem myši **SmartCaptionExpression** položky a vyberte **upravit**.  
  
12. Zadejte `(.*)` pro hodnotu. To bude odpovídat celý řetězec.  
  
13. Klikněte pravým tlačítkem myši **SmartCaptionReplacement** položky a vyberte **upravit**.  
  
14. Zadejte `$1` pro hodnotu. Tím je nahrazena řetězec s odpovídající hodnotou, což je celý řetězec tak, aby zůstane beze změny.  
  
    Při příštím přetáhnete položky z **zdroje dat** okně titulek popisky jsou vytvořeny pomocí titulků beze změny.  
  
## <a name="see-also"></a>Viz také  
[Vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)