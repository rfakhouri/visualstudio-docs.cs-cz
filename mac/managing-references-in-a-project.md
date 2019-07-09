---
title: Správa odkazů v projektu
description: Tento článek popisuje, jak Správa odkazů v projektu v sadě Visual Studio pro Mac
author: jmatthiesen
ms.author: jomatthi
ms.date: 05/06/2018
ms.assetid: 4AD51385-B0A8-4BA7-B2D4-BF2BD167A142
ms.openlocfilehash: a14630c5448632a939e1768040b910caf6276c2a
ms.sourcegitcommit: 7fbfb2a1d43ce72545096c635df2b04496b0be71
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/09/2019
ms.locfileid: "67692921"
---
# <a name="managing-references-in-a-project"></a>Správa odkazů v projektu

Visual Studio for Mac obsahuje dva prostředky přidáte další odkazy do projektu:

![Odkazy na projekty](media/projects-and-solutions-image10.png)

Toto jsou:

* Odkazy
* Balíčky Nuget (přidané prostřednictvím složku Packages)

Kromě toho odkazů na webové a nativní odkazy můžete také přidat do jakéhokoli projektu.

## <a name="assembly-references"></a>Odkazy na sestavení

Každé platformě Xamarin se dodává s více než deseti sestavení. Ne všechny tyto balíčky sestavení je odkazováno v projektu ve výchozím nastavení.

Chcete-li upravit balíčky, které je odkazováno v projektu, použijte **upravit odkazy** dialogové okno, které lze zobrazit dvojitým kliknutím na odkazy na složku, nebo výběrem **upravit odkazy** na jeho kontextu Nabídka Akce:

![Dialogové okno odkazy na sestavení](media/projects-and-solutions-image11.png)

Informace o sestavení dostupných pro každé rozhraní, Xamarin, najdete [dostupných sestavení](https://developer.xamarin.com/guides/cross-platform/advanced/available-assemblies/) průvodce.

## <a name="nuget"></a>NuGet

Správce balíčků NuGet je nejoblíbenější Správce balíčků pro vývoj na platformě .NET. Visual Studio pro Mac podpora NuGet umožňuje vyhledat balíčky k přidání do projektu.

Chcete-li to provést, klikněte pravým tlačítkem na **balíčku** složky v oblasti řešení a vyberte možnost přidat balíčky.

Další informace o použití balíčku NuGet je součástí [balíček včetně NuGet ve vašem projektu](nuget-walkthrough.md) návodu.

## <a name="see-also"></a>Viz také:

- [Správa odkazů (Visual Studio na Windows)](/visualstudio/ide/managing-references-in-a-project)
- [Přidání odkazů pomocí nástroje NuGet a sady extension SDK (Visual Studio na Windows)](/visualstudio/ide/adding-references-using-nuget-versus-an-extension-sdk)