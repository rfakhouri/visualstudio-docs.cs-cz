---
title: 'Postupy: Změna výstupního adresáře sestavení'
ms.date: 05/15/2019
ms.technology: vs-ide-compile
ms.topic: conceptual
helpviewer_keywords:
- output directory, changing
ms.assetid: a8333c89-afb2-4b1d-b2e2-9146da852402
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b0fda2363ec63572f29c6687cc10ee9a7ee06c76
ms.sourcegitcommit: 283f2dbce044a18e9f6ac6398f6fc78e074ec1ed
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/16/2019
ms.locfileid: "65805053"
---
# <a name="how-to-change-the-build-output-directory"></a>Postupy: Změna výstupního adresáře sestavení

Můžete zadat umístění výstupu generovaného ve vašem projektu na základě podle konfigurace (pro ladění, vydání nebo obojí).

## <a name="change-the-build-output-directory"></a>Změna výstupního adresáře sestavení

1. Otevření stránek vlastností projektu, klikněte pravým tlačítkem na uzel projektu v **Průzkumníka řešení** a vyberte **vlastnosti**.

2. Vyberte příslušnou kartu podle typu projektu:

   - Pro C#, vyberte **sestavení** kartu.
   - V jazyce Visual Basic, vyberte **kompilaci** kartu.
   - Pro C++ nebo JavaScript, vyberte **Obecné** kartu.

3. V rozevíracího seznamu v horní části konfigurace zvolte konfiguraci, jejíž výstup chcete změnit umístění souboru (**ladění**, **vydání**, nebo **všechny konfigurace**).

4. Vyhledejte položku výstupní cestu na stránce&mdash;se liší v závislosti na typu vašeho projektu:

   - **Výstupní cesta** pro C# a projekty jazyka JavaScript
   - **Výstupní cesta sestavení** pro projekty jazyka Visual Basic
   - **Výstupní adresář** vizuálu C++ projekty

   Zadejte cestu a generovat výstup (absolutní nebo relativní k adresáři projektu kořenový), nebo zvolte **Procházet** a místo toho přejděte do této složky.

   ![Výstupní cesta k vlastnosti pro sadu Visual Studio C# projektu](media/output-path.png)

> [!TIP]
> Pokud výstup není generována umístění, které jste zadali, ujistěte se, že vytváříte odpovídající konfiguraci (například **ladění** nebo **vydání**) tak, že ji vyberete na panelu nabídek Visual Studio.
>
> ![Sestavení pro výběr konfigurace v aplikaci Visual Studio 2019](media/build-configuration-chooser.png)

## <a name="see-also"></a>Viz také:

- [Stránka sestavení, Návrhář projektu (C#)](../ide/reference/build-page-project-designer-csharp.md)
- [Stránka Obecné vlastností (projekt)](/cpp/ide/general-property-page-project)
- [Kompilace a sestavení](../ide/compiling-and-building-in-visual-studio.md)