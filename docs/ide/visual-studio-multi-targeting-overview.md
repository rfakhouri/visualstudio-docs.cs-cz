---
title: Cílové rozhraní .NET Framework v sadě Visual Studio
ms.date: 02/06/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- targeting .NET Framework [Visual Studio]
- multi-targeting [Visual Studio]
- multitargeting [Visual Studio]
- framework targeting [Visual Studio]
- .NET framework targeting [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
ms.openlocfilehash: cba93b86d6ecebf249e11d18bd6e4b6b86e59fda
ms.sourcegitcommit: a8e01952be5a539104e2c599e9b8945322118055
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/03/2018
---
# <a name="visual-studio-multi-targeting-overview"></a>Přehled cílení na více Visual Studio

V sadě Visual Studio můžete zadat verzi nebo profil rozhraní .NET Framework, který chcete mít váš projekt. Pro aplikaci spustit v jiném počítači, Framework verze cíle aplikace musí být kompatibilní s verzí Frameworku, který je nainstalován v počítači.

Můžete také vytvořit řešení, které obsahují projekty tento cíl různé verze rozhraní. Cílení na Framework pomáhá zaručit, že aplikace bude používat jenom funkce, které jsou k dispozici v zadaná verze rozhraní.

> [!TIP]
> Také můžete určit cílovou aplikací pro různé platformy. Další informace najdete v tématu [cílení na více verzí](../msbuild/msbuild-multitargeting-overview.md).

## <a name="framework-targeting-features"></a>Framework cílení na funkce

Cílení na Framework zahrnuje následující funkce:

- Při otevření projektu, jehož cílem dřívější verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], Visual Studio automaticky upgradovat nebo nechte cíl jako-je.

- Když vytvoříte projekt, můžete zadat verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] , kterou chcete cílit.

- Můžete změnit verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] existující projekt, cílem.

- Můžete vybrat jinou verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] v každé z několika projektů ve stejném řešení.

- Když změníte verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] který cíle projektu, [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] provede požadované změny odkazů a konfigurační soubory.

Pokud pracujete na projektu, jehož cílem dřívější verzi [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], Visual Studio dynamicky změní vývojového prostředí, následujícím způsobem:

- Filtruje položky v **přidat novou položku** dialogové okno, **přidat nový odkaz** dialogové okno a **přidat odkaz na službu** dialogové okno vynechat volby, které nejsou k dispozici v Cílová verze.

- Filtruje vlastní ovládací prvky v **sada nástrojů** odeberte ty, které nejsou k dispozici v cílové verzi a zobrazit pouze nejnovější ovládacích prvků, když jsou k dispozici více ovládacích prvků.

- Filtruje **IntelliSense** vynechat jazykové funkce, které nejsou k dispozici v cílové verzi.

- Filtruje vlastnosti v **vlastnosti** okno na ty, které nejsou k dispozici v cílové verzi vynechejte.

- Filtruje možností v nabídce Možnosti, které nejsou k dispozici v cílové verzi vynechat.

- Pro sestavení používá verzi kompilátor a možnosti kompilátoru, které jsou vhodné pro cílovou verzi.

> [!NOTE]
> Cílení na Framework nezaručuje, bude vaše aplikace správně spuštěn. Vaše aplikace a ujistěte se, že je spuštěna s cílovou verzi, musíte otestovat. Cílem nemůže framework verze starší než rozhraní .NET Framework 2.0.

## <a name="select-a-target-framework-version"></a>Vyberte cílová verze framework

Když vytvoříte projekt, vyberte cílová verze rozhraní .NET Framework v **nový projekt** dialogové okno. Seznam dostupných rozhraní obsahuje verze nainstalované framework, které platí pro typ vybrané šablony. Pro typy šablon, které nevyžadují rozhraní .NET Framework, například .NET Core šablony, **Framework** rozevíracího seznamu skryt.

![Framework rozevíracího seznamu v dialogovém okně Nový projekt](media/vside-newproject-framework.png)

V existujícího projektu, můžete změnit cíl [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] verzi v dialogovém okně Vlastnosti projektu. Další informace najdete v tématu [postupy: cílení na verzi rozhraní .NET Framework](../ide/how-to-target-a-version-of-the-dotnet-framework.md).

## <a name="resolve-system-and-user-assembly-references"></a>Vyřešit systému a uživatel odkazy na sestavení

Chcete-li cílové verze rozhraní .NET Framework, musíte nejprve nainstalovat odkazy na příslušné sestavení. Si můžete stáhnout na vývojáře sady pro různé verze rozhraní .NET Framework [.NET stáhne](https://www.microsoft.com/net/download/windows) stránky.

**Přidat odkaz na** dialogové okno zakáže sestavení systému, které se netýkají cíl [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] verze tak, že není možné je přidat do projektu nechtěně. (Sestavení systému *.dll* soubory, které jsou součástí [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] verzi.) Odkazy, které patří do framework verzi, která je novější než verze cílové nevyřeší a ovládací prvky, které jsou závislé na takový odkaz nelze přidat. Pokud chcete povolit odkazu, obnovit [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] cíl, které obsahuje odkaz na projekt.  Další informace najdete v tématu [postupy: cílení na verzi rozhraní .NET Framework](../ide/how-to-target-a-version-of-the-dotnet-framework.md).

Další informace o odkazy na sestavení najdete v tématu [přeložit sestavení v době návrhu](../msbuild/resolving-assemblies-at-design-time.md).

## <a name="enable-linq"></a>Povolit LINQ

Pokud cílíte rozhraní .NET Framework 3.5 nebo novější, odkaz na **System.Core** a import úrovni projektu pro <xref:System.Linq> (v jazyce Visual Basic pouze) se přidávají automaticky. Pokud chcete používat funkce LINQ, je nutné také aktivovat `Option Infer` na (v pouze v jazyce Visual Basic). Referenční dokumentace a import se automaticky odeberou, když si změnit cíl na starší verzi rozhraní .NET Framework. Další informace najdete v tématu [pracovat s dotazy LINQ](/dotnet/csharp/tutorials/working-with-linq).

## <a name="see-also"></a>Viz také

- [Cílení na více verzí (MSBuild)](../msbuild/msbuild-multitargeting-overview.md)
- [Postupy: změnit cílový framework a platforma nástrojů (C++)](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)