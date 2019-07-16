---
title: -Vyčistit (devenv.exe) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- builds [Team System], cleaning files
- clean Devenv switch
- /clean Devenv switch
- Devenv, /clean switch
ms.assetid: 79929dfd-22c9-4cec-a0d0-a16f15b8f7e4
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: e1c32e062cf2a5406f235133fb646a16d21707cb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68190413"
---
# <a name="clean-devenvexe"></a>/Clean (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vyčistí všechny zprostředkující soubory a výstupní adresáře.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
devenv FileName /Clean [ /project projectnameorfile [/projectconfig name ] ]  
```  
  
## <a name="arguments"></a>Arguments  
 `FileName`  
 Povinný parametr. Úplná cesta a název souboru řešení nebo soubor projektu.  
  
 / Project `ProjName`  
 Volitelné. Cesta a název souboru projektu v rámci řešení. Můžete zadat relativní cestu z `SolutionName` složku do souboru projektu nebo zobrazované jméno projektu, nebo úplnou cestu a název souboru projektu.  
  
 / projectconfig `ProjConfigName`  
 Volitelné. Název projektu sestavení konfigurace, která se použije při čištění `/project` s názvem.  
  
## <a name="remarks"></a>Poznámky  
 Tento přepínač provádí stejnou funkci jako **Vyčistit řešení** příkazu nabídky v rámci integrovaného vývojového prostředí (IDE).  
  
 Uzavření řetězců, které obsahují mezery v dvojitých uvozovkách.  
  
 Souhrnné informace o vyčistí a sestavení, včetně chyb, mohou být zobrazeny v **příkaz** okna, nebo do jakéhokoli souboru protokolu zadaný `/out` přepnout.  
  
## <a name="example"></a>Příklad  
 Vyčistí v prvním příkladu `MySolution` řešení pomocí výchozí konfigurace zadaná v souboru řešení.  
  
 V druhém příkladu vyčistí projektu `CSharpConsoleApp`, použije `Debug` konfigurace sestavení projektu v rámci `Debug` konfigurace řešení `MySolution`.  
  
```  
Devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /Clean  
  
devenv "C:\Documents and Settings\someuser\My Documents\Visual Studio\Projects\MySolution\MySolution.sln" /Clean /project "CSharpWinApp\CSharpWinApp.csproj" /projectconfig "Debug"   
```  
  
## <a name="see-also"></a>Viz také  
 [Přepínače příkazového řádku nástroje devenv](../../ide/reference/devenv-command-line-switches.md)   
 [/ Sestavení (devenv.exe)](../../ide/reference/build-devenv-exe.md)   
 [/ Sestavení (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)   
 [/ Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)
