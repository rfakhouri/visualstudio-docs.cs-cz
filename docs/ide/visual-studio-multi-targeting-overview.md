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
ms.openlocfilehash: cb7af190ac7fc5d4d5ce547029689f6c902a6e4f
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2019
ms.locfileid: "66747626"
---
# <a name="framework-targeting-overview"></a>Přehled cílení na rozhraní Framework

V sadě Visual Studio můžete určit verzi rozhraní .NET, který má váš projekt zaměřit. Pro aplikace rozhraní .NET Framework pro spuštění v jiném počítači, verzi rozhraní framework, cíle, které aplikace musí být kompatibilní s verzí rozhraní framework, který je nainstalován v počítači.

Další informace o cílové architektury, najdete v části [platforem](/dotnet/standard/frameworks).

Můžete také vytvořit řešení, které obsahuje projekty zaměřené na různé verze rozhraní .NET. Cílení rozhraní pomáhá zaručit, že aplikace používá pouze funkce, které jsou k dispozici ve verzi zadaného rámce.

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

V existujícím projektu můžete změnit cílovou verzi rozhraní .NET v dialogovém okně Vlastnosti projektu. Další informace najdete v tématu [jak: Cílení na verzi .NET](../ide/how-to-target-a-version-of-the-dotnet-framework.md).

## <a name="resolve-system-and-user-assembly-references"></a>Přeložit odkazy na sestavení systémových a uživatelských

K cílení na určitou verzi rozhraní .NET, musíte nejprve nainstalovat odpovídající odkazy na sestavení. Můžete stáhnout balíčky pro vývojáře pro různé verze rozhraní .NET [.NET stáhne](https://www.microsoft.com/net/download/windows) stránky.

Pro projekty .NET Framework **přidat odkaz** dialogové okno zakáže sestavení systému, které se netýkají cílové verze rozhraní .NET tak, že není možné je přidat neúmyslně do projektu. (Systémová sestavení jsou *.dll* soubory, které jsou zahrnuty v rozhraní .NET Framework verze.) Odkazy, které patří do verze rozhraní, která je vyšší než cílová verze, neposkytne řešení a ovládací prvky, které jsou závislé na takovém odkazu nelze přidat. Pokud chcete povolit takový odkaz, obnovení, který obsahuje odkaz na cílové rozhraní .NET Framework projektu. Další informace najdete v tématu [jak: Cílení na určitou verzi rozhraní framework](../ide/how-to-target-a-version-of-the-dotnet-framework.md).

Další informace o odkazech na sestavení naleznete v tématu [přeložit sestavení v době návrhu](../msbuild/resolving-assemblies-at-design-time.md).

## <a name="enable-linq"></a>Povolení jazyka LINQ

Pokud je cílem rozhraní .NET Framework 3.5 nebo novější, odkaz na **System.Core** a import na úrovni projektu pro <xref:System.Linq> (v pouze v jazyce Visual Basic) jsou přidány automaticky. Pokud chcete používat funkce LINQ, musíte také zapnout `Option Infer` na (v pouze v jazyce Visual Basic). Reference a import jsou automaticky odebrány při změně cíle na starší verzi rozhraní .NET Framework. Další informace najdete v tématu [pracovat s technologií LINQ](/dotnet/csharp/tutorials/working-with-linq).

## <a name="see-also"></a>Viz také:

- [Cílové architektury](/dotnet/standard/frameworks)
- [Cílení na více verzí (MSBuild)](../msbuild/msbuild-multitargeting-overview.md)
- [Postupy: Upravit na cílové rozhraní framework a sadu nástrojů platformy (C++)](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)