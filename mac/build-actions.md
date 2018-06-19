---
title: Akce sestavení
description: Tento článek popisuje různé akce sestavení, které lze použít pro projekty C#
author: asb3993
ms.author: amburns
ms.date: 05/06/2018
ms.assetid: 5399BCB1-E317-4C7B-87B1-C531E985DE6E
ms.openlocfilehash: 889414d391a4a894879399317d782df58a8bacb3
ms.sourcegitcommit: 33c954fbc8e05f7ba54bfa2c0d1bc1f9bbc68876
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
ms.locfileid: "33865003"
---
# <a name="build-actions"></a>Akce sestavení

Všechny soubory v sadě Visual Studio pro projekt Mac mají akce sestavení, která určuje, co se stane do souboru během sestavení. Ty lze nastavit tak, že kliknete pravým tlačítkem na libovolný soubor a procházení k **akce sestavení**, jak je uvedeno dále:

![Výběr kompilace sestavení akce fom Průzkumníku](media/projects-and-solutions-image1.png)

Některé nejběžnější pro akce sestavení pro projekty C# jsou:

* **Žádný** -soubor není součástí sestavení žádným způsobem – je právě zahrnutý v projektu pro snadný přístup z prostředí IDE.
* **Kompilace** – soubor se předá kompilátor jazyka C# jako zdrojový soubor.
* **EmbeddedResource** – soubor se předají do kompilátoru jazyka C# jako prostředek má být vložen v sestavení. `System.Reflection` Oboru názvů lze potom použít pro čtení tohoto souboru ze sestavení.
* **Obsahu** – projekty ASP.NET pro tyto soubory budou zahrnuty jako součást lokality při nasazení. Pro Xamarin.iOS a Xamarin.Mac projekty budete mít obsažené v sady prostředků aplikace.

Je možné vybrat více než jeden soubor v Průzkumníku řešení umožňují nastavit akce sestavení pro mnoho souborů zároveň.

K dispozici je také akce sestavení pro konkrétní projekty. Například Xamarin.iOS projekty mít **BundleResource** sestavení akce, která se přidá soubor jako součást sady prostředků aplikace. Informace o konkrétní sestavení akce Xamarin.Android najdete v [proces sestavení](/xamarin/android/deploy-test/building-apps/build-process#Build_Actions) průvodce.