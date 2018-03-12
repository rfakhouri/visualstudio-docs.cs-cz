---
title: "Pomocí návrháře pracovních postupů starší | Microsoft Docs"
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Visual Studio 2005 Extensions for Windows Workflow Foundation, about
ms.assetid: 7af53077-afd7-465f-9c1d-b387e9d4f216
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: a042d98019b7f618792f7a9104d262362a4e6e3d
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/12/2018
---
# <a name="using-the-legacy-workflow-designer"></a>Pomocí návrháře pracovních postupů starší verze
Starší verze [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] poskytované [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] lze použít k cíli [!INCLUDE[netfx35_long](../workflow-designer/includes/netfx35_long_md.md)] nebo [!INCLUDE[vstecwinfx](../workflow-designer/includes/vstecwinfx_md.md)].

 Je přístupný výběrem buď **rozhraní .NET Framework 3.0** možnost nebo **rozhraní .NET Framework 3.5** možnost v rozevíracím seznamu v horní části **nový projekt** okno. Výchozí možnost v [!INCLUDE[vs2010](../misc/includes/vs2010_md.md)] je **rozhraní .NET Framework 4** sloužící k vytvoření [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] aplikacích, které cílí [!INCLUDE[netfx40_short](../workflow-designer/includes/netfx40_short_md.md)].

 [!INCLUDE[wfd2](../workflow-designer/includes/wfd2_md.md)] Poskytuje způsob, jak vytvořit graficky [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] aplikace, které používají známé [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] uživatelské rozhraní. [!INCLUDE[wf](../workflow-designer/includes/wf_md.md)] aplikace se skládají z kroků procesu pracovního postupu nazývají aktivity. Pokud chcete vytvořit pracovní postup, tvoří aktivity na návrhovou plochu přetažením návrháře jejich odpovídajících aktivit z **sada nástrojů** na návrhovou plochu.

 Následující tabulka uvádí některé klíčové funkce [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] pro Windows Workflow Foundation.

|Funkce|Popis|
|-------------|-----------------|
|Aktivita – přetažení|Přetáhněte aktivity z **sada nástrojů** na návrhovou plochu vytvoření pracovního postupu.|
|prohlížeč vlastností|Standardní **vlastnosti** okno v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] slouží ke konfiguraci vlastností aktivity.|
|Lupa|Dalekohledem **úroveň přiblížení** ikona se nachází pod svislého posuvníku na pravé straně návrhovou plochu. Klikněte Dalekohled a vyberte procento přiblížení způsobí obrázek pracovního postupu pro přiblížení či oddálení. Můžete také **Panoramování** možnosti kurzoru ikonu lupy pro přiblížení a oddálení.|
|Posouvání|**Panoramování** ikonu, kruh, který obsahuje čtyři křížového šipky směřující do čtyř směrů, se nachází pod svislého posuvníku na pravé straně návrhové plochy pod ikona přiblížení Dalekohled aplikace. Pokud kliknete na ikonu pan, místní nabídky nabízí následující možnosti kurzoru:<br /><br /> -Na **přiblížit** lupy kurzoru umožňuje přiblížit kliknutím na návrhovou plochu.<br />-Na **Oddálit** lupy kurzoru umožňuje oddálení kliknutím na návrhovou plochu.<br />-Na **navigační nástroj** ruční kurzoru umožňuje "získat" a posunutí zobrazení pracovního postupu v návrhovou plochu.<br />-Na **výchozí** šipku kurzoru umožňuje z jiných kurzory přepněte zpět na výchozí šipku kurzor.|
|Automatické posouvání|Pokud máte velké pracovní postup, můžete umístit aktivitu nad rámec viditelné zobrazení návrhu útoku. [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Umožňuje přetáhněte aktivitu směrem od okraje na návrhovou plochu nejblíže k kam chcete umístit aktivity. Zobrazení plochy návrhu automaticky posune v tomto směru.|
|Inteligentní značky|Aktivity, které jsou konfigurovány není úplně nebo není řádně označené ikonou vykřičníku. Můžete kliknutím na ikonu a najdete v rozevíracím seznamu je konfigurace, které existují na aktivity. Pak můžete použít **vlastnosti** okno správně konfigurovat aktivity. Pokud se všechny vlastnosti jsou platné pro aktivity, vykřičník ikona zmizí.|

## <a name="see-also"></a>Viz také

- [Vývoj pracovních postupů](http://go.microsoft.com/fwlink?LinkID=65010)