---
title: Cílové rozhraní .NET Framework
ms.date: 02/06/2018
ms.topic: conceptual
helpviewer_keywords:
- targeting .NET Framework [Visual Studio]
- framework targeting [Visual Studio]
- .NET framework targeting [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: b652c603cd98f9c9ec9366a225971485def187b6
ms.sourcegitcommit: d4920babfc3d24a3fe1d4bf446ed3fe73b344467
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/17/2019
ms.locfileid: "67160145"
---
# <a name="framework-targeting-overview"></a>Přehled cílení na rozhraní Framework

V sadě Visual Studio můžete určit verzi rozhraní .NET, který má váš projekt zaměřit. Cílení rozhraní pomáhá zaručit, že aplikace používá pouze funkce, které jsou k dispozici ve verzi zadaného rámce. Pro aplikace rozhraní .NET Framework pro spuštění v jiném počítači, verzi rozhraní framework, cíle, které aplikace musí být kompatibilní s verzí rozhraní framework, který je nainstalován v počítači.

Řešení sady Visual Studio může obsahovat projekty, které cílí různé verze rozhraní .NET.

Další informace o cílové architektury, najdete v části [platforem](/dotnet/standard/frameworks).

> [!TIP]
> Můžete také směrovat aplikace pro různé platformy. Další informace najdete v tématu [cílení na více verzí](../msbuild/msbuild-multitargeting-overview.md).

## <a name="framework-targeting-features"></a>Funkce cílení rozhraní Framework

Cílení rozhraní zahrnuje následující funkce:

- Když otevřete projekt, který cílí na dřívější verzi rozhraní framework, Visual Studio může automaticky upgradovat projekt nebo ponechat cíl jako-je.

- Při vytváření projektu rozhraní .NET Framework, můžete určit verzi rozhraní .NET Framework, kterou chcete cílit.

- Je možné [cílí na více platforem](/dotnet/standard/frameworks#how-to-specify-target-frameworks) v jednom projektu.

- Můžete cílit jinou verzi rozhraní .NET v různé projekty ve stejném řešení.

- Můžete změnit verzi rozhraní .NET, která existující projekt cílí.

   Pokud změníte verzi .NET, která projekt cílí, Visual Studio vytvoří všechny požadované změny odkazů a konfiguračních souborů.

Když pracujete na projektu, který cílí na dřívější verzi rozhraní framework, Visual Studio dynamicky změny ve vývojovém prostředí, následujícím způsobem:

- Filtruje položky **přidat novou položku** dialogovém okně **přidat nový odkaz** dialogovém okně a **přidat odkaz na službu** kde vynechává volby, které nejsou k dispozici v Cílová verze.

- Filtruje vlastní ovládací prvky v **nástrojů** a odeberte ty, které nejsou dostupné v cílených verzích zobrazil pouze nejnovější ovládací prvky, když jsou k dispozici více ovládacích prvků.

- Filtruje **IntelliSense** která vynechává funkce jazyka, které nejsou dostupné v cílených verzích.

- Filtruje vlastnosti v **vlastnosti** okno, aby byly vynechány ty, které nejsou dostupné v cílených verzích.

- Filtruje možnosti nabídky, aby byly vynechány možnosti, které nejsou dostupné v cílených verzích.

- V případě sestavení používá verzi kompilátoru a možnosti kompilátoru, které jsou vhodné pro cílovou verzi.

> [!NOTE]
> - Cílení rozhraní není zárukou, že vaše aplikace bude pracovat správně. Je nutné otestovat vaši aplikaci a ujistit se, že běží před cílovou verzi.
> - Nelze zaměřit verze nižší než rozhraní .NET Framework 2.0.

## <a name="select-a-target-framework-version"></a>Vyberte cílovou verzi rozhraní framework

Při vytváření projektu rozhraní .NET Framework, můžete vybrat cílovou verzi rozhraní .NET Framework, po výběru šablony projektu. Seznam dostupných rozhraní obsahuje nainstalované verze architektur, které se dají použít pro typ vybrané šablony. Pro šablony projektů rozhraní .NET Framework, například šablony .NET Core **Framework** rozevíracím seznamu nezobrazí.

::: moniker range="vs-2017"

![Rozhraní Framework rozevírací seznam v sadě VS 2017](media/vside-newproject-framework.png)

::: moniker-end

::: moniker range=">=vs-2019"

![Rozevírací seznam Framework v VS 2019](media/vs-2019/configure-new-project-framework.png)

::: moniker-end

## <a name="change-the-target-framework"></a>Změnit cílovou architekturu

V jazyce Visual Basic se existující C#, nebo F# projektu změnit cílovou verzi rozhraní .NET v dialogovém okně Vlastnosti projektu. Informace o tom, jak změnit cílovou verzi pro C++ projektů, naleznete v tématu [úpravy v cílové rozhraní framework a sadu nástrojů platformy](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset) místo.

1. V **Průzkumníka řešení**, otevřete nabídku klikněte pravým tlačítkem na projekt, který chcete změnit a klikněte na tlačítko **vlastnosti**.

1. V levém sloupci **vlastnosti** okna, vyberte **aplikace** kartu.

   ![Karta aplikace vlastnosti projektu](../ide/media/vs_slnexplorer_properties_applicationtab.png)

   > [!NOTE]
   > Po vytvoření aplikace pro UPW, nelze změnit cílenou verzi systému Windows nebo .NET.

1. V **Cílová architektura** , zvolte verzi, která chcete.

1. V dialogovém okně ověřování, který se zobrazí, zvolte **Ano** tlačítko.

   Projekt se uvolní. Až se znovu načte, zaměřuje verzi rozhraní .NET, kterou jste vybrali.

> [!NOTE]
> Pokud váš kód obsahuje odkazy na jinou verzi rozhraní .NET než ten, který jste určili, mohou se zobrazit chybové zprávy při kompilaci či spuštění kódu. Chcete-li vyřešit tyto chyby, upravte odkazy. Zobrazit [.NET řešení potíží s cílením](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md).

> [!TIP]
> V závislosti na cílové rozhraní lze znázornit v souboru projektu následujícím způsobem:
>
> - Pro .NET Core aplikace: `<TargetFramework>netcoreapp2.1</TargetFramework>`
> - Pro aplikace .NET Standard: `<TargetFramework>netstandard2.0</TargetFramework>`
> - Pro .NET Framework aplikace: `<TargetFrameworkVersion>v4.7.2</TargetFrameworkVersion>`

## <a name="resolve-system-and-user-assembly-references"></a>Přeložit odkazy na sestavení systémových a uživatelských

K cílení na určitou verzi rozhraní .NET, musíte nejprve nainstalovat odpovídající odkazy na sestavení. Můžete stáhnout balíčky pro vývojáře pro různé verze rozhraní .NET [.NET stáhne](https://www.microsoft.com/net/download/windows) stránky.

Pro projekty .NET Framework **přidat odkaz** dialogové okno zakáže sestavení systému, které se netýkají cílové verze rozhraní .NET tak, že není možné je přidat neúmyslně do projektu. (Systémová sestavení jsou *.dll* soubory, které jsou zahrnuty v rozhraní .NET Framework verze.) Odkazy, které patří do verze rozhraní, která je vyšší než cílová verze, neposkytne řešení a ovládací prvky, které jsou závislé na takovém odkazu nelze přidat. Pokud chcete povolit takový odkaz, obnovení, který obsahuje odkaz na cílové rozhraní .NET Framework projektu.

Další informace o odkazech na sestavení naleznete v tématu [přeložit sestavení v době návrhu](../msbuild/resolving-assemblies-at-design-time.md).

## <a name="enable-linq"></a>Povolení jazyka LINQ

Pokud je cílem rozhraní .NET Framework 3.5 nebo novější, odkaz na **System.Core** a import na úrovni projektu pro <xref:System.Linq> (v pouze v jazyce Visual Basic) jsou přidány automaticky. Pokud chcete používat funkce LINQ, musíte také zapnout `Option Infer` na (v pouze v jazyce Visual Basic). Reference a import jsou automaticky odebrány při změně cíle na starší verzi rozhraní .NET Framework. Další informace najdete v tématu [pracovat s technologií LINQ](/dotnet/csharp/tutorials/working-with-linq).

## <a name="see-also"></a>Viz také:

- [Cílové architektury](/dotnet/standard/frameworks)
- [Cílení na více verzí (MSBuild)](../msbuild/msbuild-multitargeting-overview.md)
- [Postupy: Upravit na cílové rozhraní framework a sadu nástrojů platformy (C++)](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)