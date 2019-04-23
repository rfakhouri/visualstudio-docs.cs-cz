---
title: 'Postupy: Ukládání a otevírání souborů s kódováním'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- Unicode, bidirectional language support
- files, encoding
- bidirectional language support, encoded files
- file encoding, bidirectional languages
ms.assetid: cb52b732-b395-4ba1-a3ef-104b3942a12a
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: fd3d7ccc248785c127c1eaf34da8840f824e4195
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60104028"
---
# <a name="how-to-save-and-open-files-with-encoding"></a>Postupy: Ukládání a otevírání souborů s kódováním

Uložte soubory s konkrétní znak kódování pro podporu obousměrných jazyků. Můžete také určit kódování při otevírání souboru, tak, aby sada Visual Studio zobrazí soubor správně.

## <a name="to-save-a-file-with-encoding"></a>Uložte soubor s kódováním

1. Z **souboru** nabídce zvolte **uložit soubor jako**a potom klikněte na tlačítko rozevíracího seznamu vedle položky **Uložit** tlačítko.

     **Pokročilé nastavení uložení** se zobrazí dialogové okno.

2. V části **kódování**, vyberte kódování použité pro soubor.

3. Volitelně můžete v rámci **once**, vyberte formát pro znaky na konec řádku.

     Tato možnost je užitečná, pokud máte v úmyslu exchange souboru s uživateli jiný operační systém.

     Pokud chcete pracovat se souborem, o kterém víte, že je zakódovaný určitým způsobem, můžete zjistit, Visual Studio použije kódování při otevření souboru. Metodu, kterou používáte závisí na tom, zda soubor součástí projektu.

## <a name="to-open-an-encoded-file-that-is-part-of-a-project"></a>Chcete-li otevřít kódovaný soubor, který je součástí projektu

1. V **Průzkumníka řešení**, klikněte pravým tlačítkem na soubor a zvolte **otevřít v**.

2. V **otevřít v programu** dialogového okna zvolte editoru otevřete soubor s.

     Mnohé editory sady Visual Studio, jako je například editor formulářů, bude automaticky rozpoznat kódování a otevřete soubor odpovídajícím způsobem. Pokud se rozhodnete editor, který umožňuje zvolit kódování, **kódování** se zobrazí dialogové okno.

3. V **kódování** dialogového okna, vyberte kódování, které by měl použít editor.

## <a name="to-open-an-encoded-file-that-is-not-part-of-a-project"></a>Chcete-li otevřít kódovaného souboru, který není součástí projektu

1. Na **souboru** nabídky, přejděte k **otevřete**, zvolte **souboru** nebo **soubor z webu**a potom vyberte soubor otevřete.

2. Klikněte na tlačítko rozevíracího seznamu vedle položky **otevřít** tlačítko a zvolte **otevřít v**.

3. Postupujte podle kroků 2 a 3 v předchozím postupu.

## <a name="see-also"></a>Viz také:

- [Kódování a zalomení řádků](encodings-and-line-breaks.md)
- [Formuláře Windows kódování a globalizace](/dotnet/framework/winforms/advanced/encoding-and-windows-forms-globalization)
- [Globalizace a lokalizace aplikací](../ide/globalizing-and-localizing-applications.md)