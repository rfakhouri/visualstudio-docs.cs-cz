---
title: Správa odkazů v projektu v sadě Visual Studio pro Mac
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.assetid: 4AD51385-B0A8-4BA7-B2D4-BF2BD167A142
ms.openlocfilehash: 75395ed0d97eba5203adf7de384bb60f71313916
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="managing-references-in-a-project"></a>Správa odkazů v projektu

Visual Studio pro Mac nabízí dva způsoby přidávání dalších odkazů na projektu:

![Odkazy na projekt](media/projects-and-solutions-image10.png)

Jsou to:

* Odkazy
* NuGets (Added prostřednictvím složce balíčků)

Kromě toho webové odkazy a nativní odkazy můžete přidat i do jakéhokoli projektu.

## <a name="assembly-references"></a>Odkazy na sestavení

Každý framework v rámci Xamarin se dodává s více než tucet sestavení. Ne všechny tyto balíčky sestavení jsou odkazovány ve vašem projektu ve výchozím nastavení. 

Chcete-li upravit balíčky, které jsou odkazované ve vašem projektu, použijte _upravit odkazy_ dialog, který lze zobrazit dvojitým kliknutím na odkazy na složku, nebo vyberte možnost Upravit odkazy na jeho kontextové nabídky akce:

![Dialogové okno odkazy na sestavení](media/projects-and-solutions-image11.png)

Informace o sestavení dostupných pro každý framework Xamarin, najdete v části [dostupné sestavení](https://developer.xamarin.com/guides/cross-platform/advanced/available-assemblies/) průvodce.

## <a name="nuget"></a>NuGet

NuGet je nejoblíbenější Správce balíčků pro .NET – vývoj. Visual Studio pro podporu NuGet pro Mac umožňuje hledat balíčky, které chcete přidat do projektu.

Chcete-li to provést, klikněte pravým tlačítkem na **balíček** složku v řešení pro a vyberte možnost přidat balíčky.

Další informace o použití balíčku NuGet je součástí [balíček včetně NuGet ve vašem projektu](~/nuget-walkthrough.md) návod.
