---
title: 'Postupy: Změna výstupního adresáře sestavení'
ms.date: 05/15/2019
ms.technology: vs-ide-compile
ms.topic: conceptual
helpviewer_keywords:
- output directory, changing
ms.assetid: a8333c89-afb2-4b1d-b2e2-9146da852402
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: e006be2099d5132ce7445f1e8fe74b0f2752c260
ms.sourcegitcommit: 59e5758036223ee866f3de5e3c0ab2b6dbae97b6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/23/2019
ms.locfileid: "68416802"
---
# <a name="how-to-change-the-build-output-directory"></a>Postupy: Změna výstupního adresáře sestavení

Můžete určit umístění výstupu generovaného vaším projektem podle konfigurace (pro ladění, vydání nebo obojí).

## <a name="change-the-build-output-directory"></a>Změna výstupního adresáře sestavení

1. Chcete-li otevřít stránky vlastností projektu, klikněte pravým tlačítkem myši na uzel projektu v **Průzkumník řešení** a vyberte možnost **vlastnosti**.

2. Vyberte příslušnou kartu na základě typu projektu:

   - V případě klikněte na kartu **sestavení.** C#
   - Pro Visual Basic vyberte kartu **kompilovat** .
   - Pro C++ nebo JavaScript vyberte kartu **Obecné** .

3. V rozevíracím seznamu konfigurace v horní části vyberte konfiguraci, jejíž umístění výstupního souboru chcete změnit (**ladění**, **vydání**nebo **všechny konfigurace**).

4. Najít položku výstupní cesty na stránce&mdash;, která se liší v závislosti na typu projektu:

   - **Výstupní cesta** pro C# projekty a projekty JavaScriptu
   - **Výstupní cesta k sestavení** pro projekty Visual Basic
   - **Výstupní adresář** pro vizuální C++ projekty

   Zadejte cestu k vygenerování výstupu (absolutní nebo relativní ke kořenovému adresáři projektu), nebo klikněte na tlačítko **Procházet** a přejděte k této složce.

   ![Vlastnost výstupní cesty pro projekt sady Visual C# Studio](media/output-path.png)

> [!TIP]
> Pokud výstup není generován do umístění, které jste určili, ujistěte se, že vytváříte odpovídající konfiguraci (například **ladění** nebo **vydání**) tak, že ji vyberete v panelu nabídek aplikace Visual Studio.
>
> ![Výběr konfigurace sestavení v aplikaci Visual Studio 2019](media/build-configuration-chooser.png)

## <a name="see-also"></a>Viz také:

- [Stránka sestavení, Návrhář projektu (C#)](../ide/reference/build-page-project-designer-csharp.md)
- [Obecná stránka vlastností (projekt)](/cpp/build/reference/general-property-page-project)
- [Kompilace a sestavení](../ide/compiling-and-building-in-visual-studio.md)