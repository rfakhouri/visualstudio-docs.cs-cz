---
title: Stránka vlastností aplikace pro aplikace UWP
ms.date: 01/23/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- AppPackage.Properties.Application
helpviewer_keywords:
- Application page [UWP project]
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- uwp
ms.openlocfilehash: a6d78c20f245f2088af8a51e2e30da3c025ae517
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
ms.locfileid: "31944408"
---
# <a name="application-property-page-uwp-projects"></a>Stránka vlastností aplikace (projekty UWP)

Použití **aplikace** na stránce vlastností zadejte sestavení projektu univerzální platformu Windows (UWP) a informace o balíčku a verzi cíl Windows 10.

![Stránka vlastností aplikace](media/application-page-uwp.png)

Abyste měli přístup **aplikace** vyberte uzel projektu v **Průzkumníku řešení**. Zvolte **projektu** > **vlastnosti** v řádku nabídek. Stránky vlastností otevřít v **aplikace** kartě.

## <a name="general-section"></a>Obecné části

**Název sestavení**&mdash;Určuje název výstupního souboru, který bude obsahovat manifest sestavení.

Přístup prostřednictvím kódu programu naleznete v tématu <xref:VSLangProj.ProjectProperties.AssemblyName%2A>.

**Výchozí obor názvů**&mdash;určuje základní obor názvů pro soubory k projektu nepřidají. Další informace o oborech názvů najdete v tématu [obory názvů (C# Průvodce programováním)](/dotnet/csharp/programming-guide/namespaces/), [obory názvů (Visual Basic)](/dotnet/visual-basic/programming-guide/program-structure/namespaces), nebo [obory názvů (C++)](/cpp/cpp/namespaces-cpp).

Přístup prostřednictvím kódu programu naleznete v tématu <xref:VSLangProj.ProjectProperties.RootNamespace%2A>.

**Informace o sestavení**&mdash;vyberete, zobrazí toto tlačítko [dialogové okno informace o sestavení](../../ide/reference/assembly-information-dialog-box.md).

**Manifest balíčku**&mdash;výběr toto tlačítko otevře návrháře manifestu. Návrháře manifestu můžete také získat přístup tak, že zvolíte _Package.appxmanifest_ souboru v **Průzkumníku řešení**. Další informace najdete v tématu [konfigurace balíčku pomocí návrháře manifestu](/windows/uwp/packaging/packaging-uwp-apps#configure-an-app-package).

## <a name="targeting-section"></a>Cílení na části

Pomocí rozevíracích seznamů v této části můžete nastavit cílovou verzi a minimální verzi Windows 10 pro vaši aplikaci. Je doporučeno, na které cílí nejnovější verzi Windows 10, a pokud vyvíjíte aplikace enterprise příliš podporují starší minimální verze. Další informace o Windows 10, kterou verzi má zvolte najdete v tématu [vyberte verzi UWP](/windows/uwp/updates-and-versions/choose-a-uwp-version).

Informace o platformě cílení v Visual Studio 2017, najdete v části [cílení na platformy](https://www.visualstudio.com/productinfo/vs2017-compatibility-vs#a-iddevelopwindows-avisual-studio-2017-support-for-windows-development).

## <a name="see-also"></a>Viz také

- [Vytvoření první aplikace UWP](/windows/uwp/get-started/your-first-app)
- [Vyberte verzi UWP](/windows/uwp/updates-and-versions/choose-a-uwp-version)