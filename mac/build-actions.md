---
title: Akce sestavení
description: Tento článek popisuje různé akce sestavení, které lze použít pro projekty jazyka C#
author: conceptdev
ms.author: crdun
ms.date: 05/06/2018
ms.assetid: 5399BCB1-E317-4C7B-87B1-C531E985DE6E
ms.openlocfilehash: a5b1175caf0ac7f6654fbe20b5300327679eccbc
ms.sourcegitcommit: 0a8ac5f2a685270d9ca79bb39d26fd90099bfa29
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2018
ms.locfileid: "51294289"
---
# <a name="build-actions"></a>Akce sestavení

Všechny soubory v sadě Visual Studio pro Mac projekt mají akci sestavení. Určuje, co se stane, do souboru během sestavování. Toto chování můžete nastavit tak, že kliknete pravým tlačítkem na jakýkoli soubor a procházením **akce sestavení**, jak je znázorněno níže:

![Výběr akce kompilace sestavení z Průzkumníka řešení](media/projects-and-solutions-image1.png)

Některé nejběžnější akce sestavení pro projekty jazyka C# jsou:

* **Žádný** – soubor není součástí sestavení žádným způsobem – je zahrnutý v projektu pro usnadnění přístupu v prostředí IDE.
* **Kompilace** – soubor se předají do kompilátoru jazyka C# jako zdrojový soubor.
* **EmbeddedResource** – soubor se předají do kompilátoru jazyka C# jako prostředek má být vložen do sestavení. [Assembly.GetManifestResourceStream](https://docs.microsoft.com/dotnet/api/system.reflection.assembly.getmanifestresourcestream), z `System.Reflection` obor názvů, je pak možné přečíst soubor ze sestavení.
* **Obsahu** – projekty ASP.NET pro tyto soubory budou zahrnuty jako součást lokality při nasazení. Pro projekty Xamarin.iOS a Xamarin.Mac budete být zahrnuty do sady prostředků aplikace.

Je možné vybrat více než jeden soubor v Průzkumníku řešení, což vám umožní nastavit akci sestavení do více souborů najednou.

K dispozici je také akce sestavení pro konkrétní projekty. Projekty Xamarin.iOS mají **BundleResource** akce, která se přidá soubor do sady prostředků aplikace v rámci sestavení. Informace o akcích Xamarin.Android konkrétní sestavení najdete v [proces sestavení](/xamarin/android/deploy-test/building-apps/build-process#Build_Actions) průvodce.