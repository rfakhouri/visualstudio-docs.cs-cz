---
title: Instalace sady Visual Studio verze vedle sebe
ms.date: 03/05/2019
ms.prod: visual-studio-windows
ms.technology: vs-isntallation
ms.topic: conceptual
helpviewer_keywords:
- side-by-side installations [Visual Studio]
- Help [Visual Studio], installing
- install multiple versions of Visual Studio
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.openlocfilehash: 22c4f24c8e97d98bb0bbe88fb998deb5929c6b7b
ms.sourcegitcommit: b7f25ae08e45fcaa84a84276b588cf6799cc7620
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/07/2019
ms.locfileid: "57567122"
---
# <a name="install-visual-studio-versions-side-by-side"></a>Instalace sady Visual Studio verze vedle sebe

Visual Studio můžete nainstalovat na počítač, který má dřívější nebo pozdější verzi sady Visual Studio již nainstalována.

::: moniker range="vs-2017"

Před instalací verzí vedle sebe, zkontrolujte následující podmínky:

* Pokud používáte Visual Studio 2017 a otevřete řešení, který byl vytvořen v sadě Visual Studio 2015, můžete později otevřít a upravit toto řešení znovu ve starší verzi, dokud jste neimplementovali žádné funkce, které jsou specifické pro Visual Studio 2017.

* Pokud se pokusíte použít Visual Studio 2017 a otevřete řešení, který byl vytvořen v sadě Visual Studio 2015 nebo starší verzi, může být potřeba upravit projekty a soubory kompatibilní se sadou Visual Studio 2017. Další informace najdete v tématu [Port, migrace a upgrade projektů sady Visual Studio](../porting/port-migrate-and-upgrade-visual-studio-projects.md?view=vs-2017) stránky.

::: moniker-end

::: moniker range=">= vs-2019"

Před instalací verzí vedle sebe, zkontrolujte následující podmínky:

* Pokud používáte Visual Studio 2019 pro otevření řešení, který byl vytvořen v sadě Visual Studio 2017, můžete později otevřít a upravit toto řešení znovu ve starší verzi, dokud jste neimplementovali žádné funkce, které jsou specifické pro Visual Studio 2019.

* Pokud se pokusíte použít Visual Studio 2019 otevřete řešení, který byl vytvořen v sadě Visual Studio 2017 nebo starší verzi, může být potřeba upravit projekty a soubory kompatibilní s Visual Studio 2019. Další informace najdete v tématu [Port, migrace a upgrade projektů sady Visual Studio](../porting/port-migrate-upgrade-visual-studio-projects-2019.md) stránky.

::: moniker-end

* Pokud odinstalujete verzi sady Visual Studio na počítači, který má více než jedna verze nainstalovaná, přidružení souborů pro Visual Studio se odeberou pro všechny verze.

* Visual Studio neprovádí automatický upgrade rozšíření vzhledem k tomu, že ne všechna rozšíření jsou kompatibilní. Je třeba přeinstalovat rozšíření od [Visual Studio Marketplace](http://go.microsoft.com/fwlink/?LinkId=178891) nebo vydavatele softwaru.

## <a name="net-framework-versions-and-side-by-side-installations"></a>Verze rozhraní .NET framework a instalace vedle sebe

Visual Basic, Visual C#a vizuální F# projekty pomocí **Cílová architektura** možnost **Návrhář projektu** k určení, kterou verzi rozhraní .NET Framework projekt používá. Pro projekt jazyka C++ můžete ručně změnit cílové rozhraní úpravou souboru .vcxproj. Další informace najdete v tématu [Kompatibilita verzí v rozhraní .NET Framework](/dotnet/framework/migration-guide/version-compatibility) stránky.

Když vytvoříte projekt, můžete určit, kterou verzi rozhraní .NET Framework je projekt cílen v **rozhraní .NET Framework** v seznamu **nový projekt** dialogové okno.

Informace specifické pro jazyk najdete v příslušném tématu v následující tabulce.

::: moniker range="vs-2017"

| Jazyk | Téma |
|--------------|-----------|
| Visual Basic | [Stránka Aplikace, Návrhář projektu (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md?view=vs-2017) |
| Visual C# | [Stránka Aplikace, Návrhář projektu (C#)](../ide/reference/application-page-project-designer-csharp.md?view=vs-2017) |
| Visual F# | [Vývoj s Vizuálem F# v sadě Visual Studio](../ide/fsharp-visual-studio.md?view=vs-2017) |
|C++ | [Postupy: Upravit na cílové rozhraní framework a sadu nástrojů platformy](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset/) |

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Instalace sady Visual Studio](install-visual-studio.md?view=vs-2017)
* [Přenos, migrace a upgrade projektů sady Visual Studio](../porting/port-migrate-and-upgrade-visual-studio-projects.md?view=vs-2017)
* [Sestavení C/C++ izolovaných aplikací a sestavení vedle sebe](/cpp/build/building-c-cpp-isolated-applications-side-by-side-assemblies/)

::: moniker-end

::: moniker range=">= vs-2019"

| Jazyk | Téma |
|--------------|-----------|
| Visual Basic | [Stránka Aplikace, Návrhář projektu (Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md?view=vs-2019) |
| Visual C# | [Stránka Aplikace, Návrhář projektu (C#)](../ide/reference/application-page-project-designer-csharp.md?view=vs-2019) |
| Visual F# | [Vývoj s Vizuálem F# v sadě Visual Studio](../ide/fsharp-visual-studio.md?view=vs-2019) |
| C++ | [Postupy: Upravit na cílové rozhraní framework a sadu nástrojů platformy](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset/) |

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>Viz také:

* [Instalace sady Visual Studio](install-visual-studio.md?view=vs-2019)
* [Přenos, migrace a upgrade projektů sady Visual Studio](../porting/port-migrate-upgrade-visual-studio-projects-2019.md)
* [Sestavení C/C++ izolovaných aplikací a sestavení vedle sebe](/cpp/build/building-c-cpp-isolated-applications-side-by-side-assemblies/)

::: moniker-end