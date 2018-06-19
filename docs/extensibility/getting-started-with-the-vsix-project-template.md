---
title: Začínáme s šablona projektu VSIX | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio SDK, VSIX project template
ms.assetid: 89fac33e-9380-4723-9b45-048a6e16f0ed
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c96c0f66792f6a7a190fb5ea69ec5727ea4f2db1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31129190"
---
# <a name="getting-started-with-the-vsix-project-template"></a>Začínáme s šablona projektu VSIX
Šablona projektu VSIX vytvoření rozšíření nebo balíček existující rozšíření pro nasazení. Šablona projektu VSIX má verze jazyka Visual Basic a Visual C# a bude nainstalován jako součást sady Visual Studio SDK.  
  
 Šablona projektu VSIX se skládá právě z source.extension.vsixmanifest souboru, který obsahuje informace o rozšíření a prostředků, které je dodáván.  
  
 Najít v šabloně projektů VSIX, je nutné nainstalovat sadu Visual Studio SDK. Další informace najdete v tématu [Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="deploying-a-custom-project-template-using-the-vsix-project-template"></a>Nasazení vlastní šablony projektu pomocí šablony projektu VSIX  
 Následující kroky ukazují, jak pomocí projektu VSIX balíček šablona projektu, který můžete sdílet s jinými vývojáři nebo odeslat do Galerie Visual Studio.  
  
1.  Vytvoření šablony projektu.  
  
    1.  Otevřete projekt, ze kterého chcete vytvořit šablonu. Tento projekt můžou být jakéhokoli typu projektu.  
  
    2.  Na **projektu** nabídky, klikněte na tlačítko **exportovat šablonu**. Postupujte podle pokynů průvodce.  
  
         Soubor ZIP je vytvořen v %USERPROFILE%\My Documents\Visual Studio  *\<verze >* šablony exportovat \My\\.  
  
2.  Vytvořte prázdný projekt VSIX.  
  
     Na **soubor** nabídky, klikněte na tlačítko **nový** a pak klikněte na **projektu**. Vyberte buď **jazyka Visual Basic** nebo **Visual C#**. V části vybraný uzel, vyberte **rozšiřitelnost**a potom vyberte **projektu VSIX**.  
  
3.  Přidejte do projektu soubor .zip. Nastavte její **kopírovat do výstupního adresáře** vlastnost `Copy Always`.  
  
4.  V **Průzkumníku řešení**, dvakrát klikněte `source.extension.vsixmanifest` soubor otevřete v **Návrhář manifestu VSIX**a potom proveďte následující změny:  
  
    -   Nastavte **název produktu** do **moje šablona projektu**.  
  
    -   Nastavte **ID produktu** do **MyProjectTemplate - 1**.  
  
    -   Nastavte **Autor** do **Fabrikam**.  
  
    -   Nastavte **popis** do **moje šablona projektu**.  
  
    -   V **prostředky** přidejte **Microsoft.VisualStudio.ProjectTemplate** zadejte a nastavit jeho cestu k názvu souboru .zip.  
  
5.  Uložte a zavřete soubor source.extension.vsixmanifest.  
  
6.  Sestavte projekt.  
  
7.  V adresáři výstup poklikejte na soubor VSIX.  
  
8.  A **instalační program VSIX** se zobrazí okno se zprávou. Postupujte podle pokynů k instalaci rozšíření.  
  
9. Zavřete Visual Studio a potom ho znovu otevřete.  
  
10. Vyberte **rozšíření a aktualizace** (na **nástroje** nabídky) a vyberte **šablony** kategorie. Jeden z dostupných rozšíření by měl být **moje šablona projektu**.  
  
11. Nová šablona projektu se zobrazí v **nový projekt** dialogové okno na stejném místě jako původní šablona projektu. Například, pokud jste vytvořili šablonu s názvem **VB konzoly** z konzolové aplikace jazyka Visual Basic, **VB konzoly** se zobrazí v podokně stejné jako Visual Basicu **konzolové aplikace**šablony.  
  
#### <a name="to-specify-the-location-of-the-template-in-the-new-project-dialog-box"></a>K určení umístění šablony v dialogovém okně Nový projekt  
  
1.  Šablona složky jsou umístěny v *Visual Studio Instalační cesta*\Common7\IDE\ProjectTemplates a *Visual Studio Instalační cesta*\Common7\IDE\ItemTemplates adresáře. Názvy oddílů nejvyšší úrovně v dialogu Nový projekt, které přesně odpovídat názvy složek šablony. Kde se liší, použijte název složky šablony.  
  
     Změňte VSIX příponu souboru .zip a pak otevřete soubor.  
  
2.  Vytvořte novou složku se stejným názvem jako části dialogového okna Nový projekt šablona by měla zobrazit v.  
  
3.  Pokud se objeví v část je šablona, vytvořte podsložky se stejným názvem.  
  
4.  Přesuňte soubor .zip šablony do nové složky.  
  
5.  Změňte příponu .zip na VSIX.  
  
6.  Otevřete VSIX manifest.  
  
7.  V manifestu VSIX, aktualizovat **Asset** cesta šablony, které se odkazuje na kořenový adresář stromové struktury, která obsahuje soubor šablony. Například pokud je šablona v \CSharp\Windows, odkaz na by měla odkazovat na \CSharp.