---
title: "Přidání přepínače příkazového řádku | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- command-line switches, adding
- command-line switches, retrieving
- IVsAppCommandLine::GetOption method
- command line, switches
ms.assetid: 8bbbd87e-76fe-4fb5-8ef9-65f5e31967cf
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d686e7b68e790c419679bf495bf08ad4cd4807e2
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="adding-command-line-switches"></a>Přidání přepínače příkazového řádku
Můžete přidat přepínače příkazového řádku, která se týkají vašeho VSPackage při devenv.exe. Použití <xref:Microsoft.VisualStudio.Shell.ProvideAppCommandLineAttribute> deklarovat název přepínač a jeho vlastnosti. V tomto příkladu se přidá MySwitch přepínač pro podtřídou třídy s názvem VSPackage **AddCommandSwitchPackage** bez argumentů a s VSPackage automaticky načíst.  
  
```csharp  
[ProvideAppCommandLine("MySwitch", typeof(AddCommandSwitchPackage), Arguments = "0", DemandLoad = 1)]  
```  
  
 V následující tabulce jsou uvedeny pojmenované parametry  
  
 Arguments  
 Počet argumentů pro přepínač. Může být "*", nebo seznam argumentů.  
  
 DemandLoad  
 VSPackage načte automaticky, pokud je nastavená na hodnotu 1, jinak hodnota nastavena na hodnotu 0.  
  
 Helpstring –  
 Řetězec nebo prostředků ID nápovědy řetězce pro zobrazení s **devenv /?**.  
  
 Název  
 Přepínač.  
  
 PackageGuid  
 Identifikátor GUID balíčku.  
  
 První hodnota argumentů je obvykle 0 nebo 1. Hodnota ' *' slouží k označení, že celý zbytek příkazového řádku je argumentem. To může být užitečné pro ladění scénáře, kde uživatel musí projít v řetězci příkazu ladicího programu.  
  
 Hodnota DemandLoad je buď `true` (1) nebo `false` (0) znamená, že VSPackage by měla být načtena automaticky.  
  
 Helpstring – hodnota je ID prostředku řetězec, který se zobrazí v devenv /? Zobrazení nápovědy. Tato hodnota by měla být ve tvaru "#nnn" kde nnn je celé číslo. Hodnota řetězce v souboru prostředků musí končit znak nového řádku.  
  
 Hodnota názvu je název přepínače.  
  
 Hodnota PackageGuid je identifikátor GUID balíčku, který implementuje tento přepínač. Prostředí IDE používá tento identifikátor GUID k nalezení VSPackage v registru, na které se vztahuje na přepínač příkazového řádku.  
  
## <a name="retrieving-command-line-switches"></a>Načítání přepínače příkazového řádku  
 Když je načten do balíčku, můžete načíst přepínače příkazového řádku pomocí následujících kroků.  
  
1.  Ve vašem VSPackage <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A> implementace, volání `QueryService` na <xref:Microsoft.VisualStudio.Shell.Interop.SVsAppCommandLine> získat <xref:Microsoft.VisualStudio.Shell.Interop.IVsAppCommandLine> rozhraní.  
  
2.  Volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsAppCommandLine.GetOption%2A> načíst přepínače příkazového řádku, které uživatel zadal.  
  
 Následující kód ukazuje, jak zjistit, zda byl zadán přepínač příkazového řádku MySwitch uživatel:  
  
```csharp  
IVsAppCommandLine cmdline = (IVsAppCommandLine)GetService(typeof(SVsAppCommandLine));  
  
int isPresent = 0;  
string optionValue = "";  
  
cmdline.GetOption("MySwitch", out isPresent, out optionValue);  
```  
  
 Je vaší povinností zkontrolujte vaše přepínače příkazového řádku pokaždé, když je načten do balíčku.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAppCommandLine>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.SetSite%2A>   
 [Přepínače příkazového řádku nástroje devenv](../ide/reference/devenv-command-line-switches.md)   
 [Nástroj CreatePkgDef](../extensibility/internals/createpkgdef-utility.md)   
 [. Pkgdef soubory](../extensibility/modifying-the-isolated-shell-by-using-the-dot-pkgdef-file.md)