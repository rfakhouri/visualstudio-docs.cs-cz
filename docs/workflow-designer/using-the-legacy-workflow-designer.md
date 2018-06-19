---
title: Pomocí návrháře pracovních postupů starší verze
ms.date: 11/04/2016
ms.topic: conceptual
ms.prod: visual-studio-dev15
ms.technology: vs-workflow-designer
helpviewer_keywords:
- Visual Studio 2005 Extensions for Windows Workflow Foundation, about
ms.assetid: 7af53077-afd7-465f-9c1d-b387e9d4f216
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 794b52c918eb727fe67d24af209d21403da18475
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31975465"
---
# <a name="using-the-legacy-workflow-designer"></a>Pomocí návrháře pracovních postupů starší verze

Starší verze zadaná v Návrháři pracovních postupů pomocí sady Visual Studio 2010 lze cílit na rozhraní .NET Framework verze 3.5 nebo WinFX.

Je přístupný výběrem buď **rozhraní .NET Framework 3.0** možnost nebo **rozhraní .NET Framework 3.5** možnost v rozevíracím seznamu v horní části **nový projekt** okno. Výchozí možnost v sadě Visual Studio 2010 je **rozhraní .NET Framework 4** sloužící k vytvoření aplikace Windows Workflow Foundation (WF), které cílí na rozhraní .NET Framework 4.

Návrhář postupu provádění poskytuje způsob, jak graficky vytvářet aplikace Windows Workflow Foundation (WF) pomocí uživatelského rozhraní známé Visual Studio. Aplikace Windows Workflow Foundation (WF) se skládají z kroků procesu pracovního postupu nazývají aktivity. Pokud chcete vytvořit pracovní postup, tvoří aktivity na návrhovou plochu přetažením návrháře jejich odpovídajících aktivit z **sada nástrojů** na návrhovou plochu.

Následující tabulka uvádí některé klíčové funkce Visual Studio pro Windows Workflow Foundation.

|Funkce|Popis|
|-------------|-----------------|
|Aktivita – přetažení|Přetáhněte aktivity z **sada nástrojů** na návrhovou plochu vytvoření pracovního postupu.|
|prohlížeč vlastností|Standardní **vlastnosti** oken v sadě Visual Studio slouží ke konfiguraci vlastností aktivity.|
|Lupa|Dalekohledem **úroveň přiblížení** ikona se nachází pod svislého posuvníku na pravé straně návrhovou plochu. Klikněte Dalekohled a vyberte procento přiblížení způsobí obrázek pracovního postupu pro přiblížení či oddálení. Můžete také **Panoramování** možnosti kurzoru ikonu lupy pro přiblížení a oddálení.|
|Posouvání|**Panoramování** ikonu, kruh, který obsahuje čtyři křížového šipky směřující do čtyř směrů, se nachází pod svislého posuvníku na pravé straně návrhové plochy pod ikona přiblížení Dalekohled aplikace. Pokud kliknete na ikonu pan, místní nabídky nabízí následující možnosti kurzoru:<br /><br /> -Na **přiblížit** lupy kurzoru umožňuje přiblížit kliknutím na návrhovou plochu.<br />-Na **Oddálit** lupy kurzoru umožňuje oddálení kliknutím na návrhovou plochu.<br />-Na **navigační nástroj** ruční kurzoru umožňuje "získat" a posunutí zobrazení pracovního postupu v návrhovou plochu.<br />-Na **výchozí** šipku kurzoru umožňuje z jiných kurzory přepněte zpět na výchozí šipku kurzor.|
|Automatické posouvání|Pokud máte velké pracovní postup, můžete umístit aktivitu nad rámec viditelné zobrazení návrhu útoku. Visual Studio umožňuje přetáhněte aktivitu směrem od okraje na návrhovou plochu nejblíže k kam chcete umístit aktivity. Zobrazení plochy návrhu automaticky posune v tomto směru.|
|Inteligentní značky|Aktivity, které jsou konfigurovány není úplně nebo není řádně označené ikonou vykřičníku. Můžete kliknutím na ikonu a najdete v rozevíracím seznamu je konfigurace, které existují na aktivity. Pak můžete použít **vlastnosti** okno správně konfigurovat aktivity. Pokud se všechny vlastnosti jsou platné pro aktivity, vykřičník ikona zmizí.|

## <a name="see-also"></a>Viz také

- [Vývoj pracovních postupů](http://go.microsoft.com/fwlink?LinkID=65010)