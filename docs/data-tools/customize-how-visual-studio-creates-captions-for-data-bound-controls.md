---
title: Přizpůsobení popisků pro ovládací prvky vázané daty
ms.date: 11/03/2017
ms.topic: conceptual
helpviewer_keywords:
- Label captions, Data Sources window
- smart captions
- captions, data-bound
- Data Sources Window, label captions
ms.assetid: 6d4d15f8-4d78-42fd-af64-779ae98d62c8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 1745aef29da9fc8efd49789f0112c903128f6f74
ms.sourcegitcommit: 11337745c1aaef450fd33e150664656d45fe5bc5
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/04/2019
ms.locfileid: "57323694"
---
# <a name="customize-how-visual-studio-creates-captions-for-data-bound-controls"></a>Úprava způsobu, kterým Visual Studio vytváří titulky pro ovládací prvky vázané daty

Při přetažení položky z [okna zdroje dat](add-new-data-sources.md#data-sources-window) do návrháře, zvláštní pozornost vstupu do play: názvy sloupců v popiscích titulek jsou přeformátována na řetězec čitelnější, pokud dvě nebo více slov nedodržují zřetězených dohromady.

::: moniker range="vs-2017"

Můžete změnit způsob, ve kterém jsou tyto popisky vytvořené tak, že nastavíte **SmartCaptionExpression**, **SmartCaptionReplacement**, a **SmartCaptionSuffix** hodnoty v **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\15.0\Data návrháři** klíč registru.

::: moniker-end

::: moniker range=">=vs-2019"

Můžete změnit způsob, ve kterém jsou tyto popisky vytvořené tak, že nastavíte **SmartCaptionExpression**, **SmartCaptionReplacement**, a **SmartCaptionSuffix** hodnoty v **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\16.0\Data návrháři** klíč registru.

::: moniker-end

> [!NOTE]
> Tento klíč registru neexistuje, dokud ho vytvoříte.

Inteligentní titulky řídí regulárních výrazů do hodnoty **SmartCaptionExpression** hodnotu. Přidávání **návrháře dat** klíč registru přepisuje výchozí regulární výraz, který řídí titulků. Další informace o formátování regulárních výrazů, naleznete v tématu [pomocí regulárních výrazů v sadě Visual Studio](../ide/using-regular-expressions-in-visual-studio.md).

Následující tabulka popisuje hodnoty registru, které řídí titulků.

|Položky registru|Popis|
|-------------------|-----------------|
|**SmartCaptionExpression**|Regulární výraz, který používáte tak, aby odpovídaly vaše postupy.|
|**SmartCaptionReplacement**|Formát, který se zobrazí všechny skupiny se shodou v **SmartCaptionExpression**.|
|**SmartCaptionSuffix**|Volitelný řetězec pro připojení za účelem titulek.|

Následující tabulka uvádí vnitřní výchozí nastavení pro tyto hodnoty registru.

|Položky registru|Výchozí hodnota|Vysvětlení|
|-------------------|-------------------|-----------------|
|**SmartCaptionExpression**|**(\\\p{Ll})(\\\p{Lu})&#124;_+**|Odpovídá znak malého písmene, za nímž následuje velkým písmenem nebo podtržítkem.|
|**SmartCaptionReplacement**|**$1 $2**|**$1** představuje libovolné znaky se shodou v první závorky výrazu a **$2** představuje libovolné znaky shoda v druhé závorky. Nahrazení je první shodu, mezeru a druhý shoda.|
|**SmartCaptionSuffix**|**:**|Hodnota představuje znak připojenou k vráceného řetězce. Například, pokud je popisek `Company Name`, přípona umožňuje `Company Name:`|

> [!CAUTION]
> Buďte velmi opatrní při teď zrovna nic nedělá v editoru registru. Registr zálohovali začnete upravovat. Pokud Editor registru používán správně, můžete způsobit vážné problémy, které mohou vyžadovat přeinstalaci operačního systému. Microsoft nezaručuje, že lze vyřešit problémy způsobující pomocí Editoru registru nesprávně. Pomocí Editoru registru na vlastní nebezpečí.
>
> Informace o zálohování, úpravy a obnovení registru, najdete v části [informací z registru Windows pro pokročilé uživatele](https://support.microsoft.com/help/256986/windows-registry-information-for-advanced-users).

## <a name="modify-the-smart-captioning-behavior-of-the-data-sources-window"></a>Upravit inteligentní titulků chování okna zdroje dat

1. Otevřete okno příkazového řádku kliknutím **Start** a potom **spustit**.

2. Typ `regedit` v **spustit** dialogové okno a klikněte na tlačítko **OK**.

3. Rozbalte **HKEY_CURRENT_USER** > **softwaru** > **Microsoft** > **VisualStudio**uzlu.

::: moniker range="vs-2017"

4. Klikněte pravým tlačítkem myši **15.0** uzel a vytvořte nový **klíč** s názvem `Data Designers`.

::: moniker-end

::: moniker range=">=vs-2019"

4. Klikněte pravým tlačítkem myši **16.0** uzel a vytvořte nový **klíč** s názvem `Data Designers`.

::: moniker-end

5. Klikněte pravým tlačítkem myši **návrháře dat** uzel a vytvořte tři nové hodnoty řetězce:

    - `SmartCaptionExpression`
    - `SmartCaptionReplacement`
    - `SmartCaptionSuffix`

6. Klikněte pravým tlačítkem myši **SmartCaptionExpression** hodnotu a vyberte **změnit**.

7. Zadejte regulární výraz, který chcete, aby **zdroje dat** okna.

8. Klikněte pravým tlačítkem myši **SmartCaptionReplacement** hodnotu a vyberte **změnit**.

9. Zadejte náhradní řetězec ve formátu tak, jak chcete zobrazit tyto vzory se dají v regulárním výrazu odpovídá.

10. Klikněte pravým tlačítkem myši **SmartCaptionSuffix** hodnotu a vyberte **změnit**.

11. Zadejte všechny znaky, které se mají zobrazit na konci titulek.

    Při příštím přetáhněte položky z **zdroje dat** okně titulek popisky jsou vytvořeny pomocí nové hodnoty registru, které jsou k dispozici.

## <a name="turn-off-the-smart-captioning-feature"></a>Vypnout funkci inteligentního titulků

1. Otevřete okno příkazového řádku kliknutím **Start** a potom **spustit**.

2. Typ `regedit` v **spustit** dialogové okno a klikněte na tlačítko **OK**.

3. Rozbalte **HKEY_CURRENT_USER** > **softwaru** > **Microsoft** > **VisualStudio**uzlu.

::: moniker range="vs-2017"

4. Klikněte pravým tlačítkem myši **15.0** uzel a vytvořte nový **klíč** s názvem `Data Designers`.

::: moniker-end

::: moniker range=">=vs-2019"

4. Klikněte pravým tlačítkem myši **16.0** uzel a vytvořte nový **klíč** s názvem `Data Designers`.

::: moniker-end

5. Klikněte pravým tlačítkem myši **návrháře dat** uzel a vytvořte tři nové hodnoty řetězce:

    - `SmartCaptionExpression`
    - `SmartCaptionReplacement`
    - `SmartCaptionSuffix`

6. Klikněte pravým tlačítkem myši **SmartCaptionExpression** položky a vyberte **změnit**.

7. Zadejte `(.*)` pro hodnotu. To se bude shodovat celý řetězec.

8. Klikněte pravým tlačítkem myši **SmartCaptionReplacement** položky a vyberte **změnit**.

9. Zadejte `$1` pro hodnotu. To nahradí řetězec odpovídající hodnotu, která je celý řetězec tak, aby zůstane beze změny.

    Při příštím přetáhněte položky z **zdroje dat** popisky titulek okna, jsou vytvořeny s verzí bez úprav titulky.

## <a name="see-also"></a>Viz také:

- [Vytvoření vazby ovládacích prvků k datům v sadě Visual Studio](../data-tools/bind-controls-to-data-in-visual-studio.md)