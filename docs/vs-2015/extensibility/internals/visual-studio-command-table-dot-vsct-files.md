---
title: Tabulky příkazů sady Visual Studio (. Soubory Vsct) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, overview
- Visual Studio command table configuration files (VSCT), overview
ms.assetid: 1313adb4-add4-4e74-90e2-f4be522f5259
caps.latest.revision: 23
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: cde3b86e19788c41df6e8f1c79a6bf829f491170
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65675248"
---
# <a name="visual-studio-command-table-vsct-files"></a>Soubory tabulek příkazů sady Visual Studio (.Vsct)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Příkaz tabulky konfigurační soubor je textový soubor, který popisuje sadu příkazů, které obsahuje VSPackage. [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] Příkaz kompilátoru tabulky (VSCT) kompiluje konfiguraci na základě XML soubory (.vsct) do soubory výstup (.cto) tabulky příkaz binary. Výsledná .cto soubory jsou stejné jako ty, které jsou vytvořeny pomocí kompilátoru tabulky (CTC) příkaz pro kompilaci .ctc konfigurační soubory. Soubory .vsct založený na formátu XML má však několik výhod, jako je například editoru XML a XML IntelliSense.  
  
 Další informace o syntaxi a sémantiku souborů .vsct najdete v tématu [návrh tabulky příkazů XML (. Soubory Vsct)](../../extensibility/internals/designing-xml-command-table-dot-vsct-files.md)  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Návrh souborů tabulky příkazů XML (.Vsct)](../../extensibility/internals/designing-xml-command-table-dot-vsct-files.md)  
 Popisuje postup návrhu soubory .vsct.  
  
 [Postupy: Vytvoření souboru .Vsct](../../extensibility/internals/how-to-create-a-dot-vsct-file.md)  
 Porovnává metody pro vytvoření souboru .vsct. Popisuje proces pro ruční vytvoření nového souboru .vsct.  
  
## <a name="related-sections"></a>Související oddíly  
 [XML schéma VSCT – referenční informace](../../extensibility/vsct-xml-schema-reference.md)  
 Obsahuje podrobné informace o každé části příkazu tabulky XML konfigurační soubor.  
  
 [Příkaz konfigurace tabulky (. Soubory CTC)](https://msdn.microsoft.com/3413dda1-f372-4669-bcf0-c64d3463842c)  
 Obsahuje přehled nepoužívané .ctc formát souboru.  
  
 [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)  
 Popisuje příkaz specifikace formátu tabulky.  
  
 [Prostředky v balíčcích VSPackage](../../extensibility/internals/resources-in-vspackages.md)  
 Popisuje způsob použití spravovaných i nespravovaných prostředků do spravovaných rozšíření VSPackages.  
  
 [Příkazy, nabídky a panely nástrojů](../../extensibility/internals/commands-menus-and-toolbars.md)  
 Vysvětluje, jak vytvářet uživatelské rozhraní, která zahrnuje nabídky, panely nástrojů a příkaz pole se seznamem.
