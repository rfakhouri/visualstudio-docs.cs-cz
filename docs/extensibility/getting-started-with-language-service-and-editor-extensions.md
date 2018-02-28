---
title: "Začínáme s jazykové služby a rozšíření editorů | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- editors [Visual Studio SDK], new - extensions
ms.assetid: 6b151891-c06d-40b1-9867-42298caa8492
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 5f7b7440ff2f42eba1d138872071d4e51d2402c1
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="getting-started-with-language-service-and-editor-extensions"></a>Začínáme se službou a rozšíření editorů jazyka
Editor rozšíření můžete použít k přidání funkcí služby jazyk například osnovy, odpovídající složené závorce, IntelliSense a žárovek vlastní programovací jazyk nebo jakýkoli typ obsahu. Můžete také přizpůsobit vzhled a chování editoru Visual Studio, například textu zvýrazňování okraje, vylepšení a další vizuální prvky. Můžete také definovat vlastní typ obsahu a určit vzhled a chování textového zobrazení, ve kterých se zobrazí obsah.  
  
 Pokud chcete začít, zápis rozšíření editorů, použijte editor šablony projektů, které jsou nainstalovány v rámci sady Visual Studio SDK. Visual Studio SDK je ke stažení sada nástrojů, které usnadňují vývoj rozšíření Visual Studia, buď pomocí VSPackages, nebo pomocí Managed Extensibility Framework (MEF).  
  
> [!NOTE]
>  Další informace o sadě Visual Studio SDK najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
 Doporučujeme, abyste před můžete psát vlastní rozšíření editorů informace o následující koncepty a technologie.  
  
## <a name="the-windows-presentation-foundation-wpf-and-editor-extensions"></a>Windows Presentation Foundation (WPF) a rozšíření editoru  
 Visual Studio editor uživatelské rozhraní (UI) je implementována pomocí Windows Presentation Foundation (WPF). WPF poskytuje zajímavé vizuální prostředí a konzistentní programovací model, který odděluje visual aspektů kód z obchodní logiky. Množství prvků grafického subsystému WPF a funkcí můžete použít při vytváření rozšíření pro editor. Další informace najdete v tématu [Windows Presentation Foundation](/dotnet/framework/wpf/index).  
  
## <a name="the-managed-extensibility-framework-mef-and-editor-extensions"></a>Spravovaná rozšíření Framework (MEF) a rozšíření editoru  
 Editoru Visual Studio používá Managed Extensibility Framework (MEF) ke správě jeho součásti a rozšíření. MEF také umožňuje vývojářům další snadno vytvářet rozšíření pro hostitelskou aplikaci jako v aplikaci Visual Studio. Ve toto rozhraní můžete definovat rozšíření podle kontraktu MEF a exportovat jako součást MEF. Hostitelskou aplikaci spravuje části součást tím, že je, je registrace a zajistit, že jsou nastavení použita na správný kontext.  
  
> [!NOTE]
>  Další informace o rozhraní MEF v editoru najdete v tématu [spravované rozhraní rozšiřitelnosti v editoru](../extensibility/managed-extensibility-framework-in-the-editor.md).  
  
## <a name="visual-studio-editor-extension-points-and-extensions"></a>Body rozšíření editoru Visual Studio a rozšíření  
 Editor rozšíření body jsou MEF součásti, které můžete přizpůsobit a rozšířit. V některých případech můžete rozšířit bodem rozšíření implementace rozhraní a export společně s správných metadat. V ostatních případech stačí deklarovat rozšíření a exportovat jako konkrétního typu.  
  
 Tady jsou některé základní typy rozšíření editoru:  
  
-   Okraje a posuvníky  
  
-   Značky  
  
-   Vylepšení  
  
-   Možnosti  
  
-   IntelliSense  
  
 Další informace o bodech rozšíření editoru najdete v tématu [služba jazyka a body rozšíření editoru](../extensibility/language-service-and-editor-extension-points.md).  
  
## <a name="deploying-editor-extensions"></a>Nasazení rozšíření editoru  
 V sadě Visual Studio nasadit rozšíření editoru přidáním soubor metadat s názvem source.extension.vsixmanifest k řešení, sestavení řešení, a pak přidáním kopie binární soubory a manifest ve složce, která se označuje k sadě Visual Studio. Soubor manifestu definuje základních faktů o rozšíření (například název, autora, verzi a typ obsahu). Další informace o souboru manifestu VSIX a implementaci rozšíření najdete v tématu [přesouvání rozšíření Visual Studia](../extensibility/shipping-visual-studio-extensions.md).  
  
 Při instalaci rozšíření na počítači, zahrnují binární soubory a manifest v podsložce složky, která se označuje k sadě Visual Studio.  
  
> [!WARNING]
>  Nemusíte si dělat starosti podrobností o manifesty a umístění nasazení, pokud použijete jednu z šablony editor rozšiřitelnosti, které jsou zahrnuté v sadě Visual Studio. Šablony obsahují vše, co je potřeba zaregistrujte a nasaďte rozšíření.  
  
## <a name="running-extensions-in-the-experimental-instance"></a>Spouštění rozšíření v experimentální instanci  
 Vaše pracovní verze sady Visual Studio můžete izolovat při vývoji rozšíření nasazením v následující složce experimentální (v systému Windows Vista a Windows 7):  
  
 *% LOCALAPPDATA %*\VisualStudio\10.0Exp\Extensions\\*společnosti*\\*ExtensionID*  
  
 kde *LOCALAPPDATA %* je název přihlášeného uživatele, *společnosti* je název společnosti, která vlastní rozšíření, a *ExtensionID* je ID rozšíření.  
  
 Pokud nasadíte rozšíření experimentální umístění, běží v režimu ladění. Druhou instanci sady Visual Studio spuštěná a názvem **Microsoft Visual Studio – experimentální instanci**.  
  
## <a name="managing-extensions"></a>Správa rozšíření  
 Rozšíření pro Visual Studio jsou uvedeny v **rozšíření a aktualizace** (na **nástroje** nabídky). Pokud testujete rozšíření v experimentální instanci, je uvedena ve **rozšíření a aktualizace** v experimentální instanci, ale není uvedený v instanci vývoj.  
  
 Další informace najdete v tématu [hledání a používání rozšíření Visual Studia](../ide/finding-and-using-visual-studio-extensions.md).  
  
## <a name="using-templates-to-create-editor-extensions"></a>Pomocí šablony pro vytvoření rozšíření editorů  
 Editor šablon můžete použít k vytvoření MEF rozšíření, která přizpůsobení třídění, vylepšení a okraje. Existuje šablon pro projekty jak C# a Visual Basic. Další informace najdete v tématu [vytváření rozšíření pomocí šablony položky Editor](../extensibility/creating-an-extension-with-an-editor-item-template.md).  
  
 Šablona projektu VSIX můžete použít také k vytvoření rozšíření. Tato šablona obsahuje pouze prvky, které jsou potřebné k nasazení jakýkoli druh rozšíření a zahrnují soubor source.extension.vsixmanifest, odkazy na požadované sestavení a soubor projektu, který zahrnuje sestavení úlohy, které umožňují nasadit rozšíření. Další informace najdete v tématu [šablona projektu VSIX](../extensibility/vsix-project-template.md).  
  
 Můžete také vytvořit editor MEF součásti z rozšíření balíček Visual Studio. Naleznete v následujících seznamech podrobnosti:  
  
-   [Návod: Použití příkazů prostředí s rozšířením editoru](../extensibility/walkthrough-using-a-shell-command-with-an-editor-extension.md)  
  
-   [Návod: Použití klávesové zkratky s rozšířením editoru](../extensibility/walkthrough-using-a-shortcut-key-with-an-editor-extension.md)  
  
## <a name="see-also"></a>Viz také  
 [Rozšiřovací body služeb jazyka a editoru](../extensibility/language-service-and-editor-extension-points.md)