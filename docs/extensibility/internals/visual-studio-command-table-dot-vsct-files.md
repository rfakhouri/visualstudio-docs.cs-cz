---
title: "Visual Studio příkaz tabulky (. Soubory Vsct) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSCT files, overview
- Visual Studio command table configuration files (VSCT), overview
ms.assetid: 1313adb4-add4-4e74-90e2-f4be522f5259
caps.latest.revision: "22"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 71a202bdb71469e4d6b46eb537147092b1ea9013
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="visual-studio-command-table-vsct-files"></a>Visual Studio příkaz tabulky (. Soubory Vsct)
Příkaz tabulky konfigurační soubor je textový soubor, který popisuje sadu příkazů, které obsahuje VSPackage. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] Příkaz tabulky (VSCT) kompilátoru kompilovaný konfiguraci na základě XML (soubory .vsct) do binární příkaz tabulky výstupní (.cto) soubory. Výsledná .cto soubory jsou stejné jako ty, které jsou vytvořené pomocí kompilátoru tabulky (CTC) příkaz zkompilovat .ctc konfigurační soubory. Soubory formátu XML .vsct však má několik výhod, jako je například editoru XML a XML IntelliSense.  
  
 Další informace o syntaxi a sémantiku .vsct souborů najdete v tématu [návrh tabulky příkaz XML (. Soubory Vsct)](../../extensibility/internals/designing-xml-command-table-dot-vsct-files.md)  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Návrh souborů tabulky příkazů XML (.Vsct)](../../extensibility/internals/designing-xml-command-table-dot-vsct-files.md)  
 Popisuje postup návrhu .vsct soubory.  
  
 [Postupy: Vytvoření souboru .Vsct](../../extensibility/internals/how-to-create-a-dot-vsct-file.md)  
 Porovná metody pro vytvoření souboru .vsct. Popisuje postup pro ruční vytvoření nového souboru .vsct.  
  
## <a name="related-sections"></a>Související oddíly  
 [XML schéma VSCT – referenční informace](../../extensibility/vsct-xml-schema-reference.md)  
 Poskytuje podrobnosti o jednotlivých částech konfigurační soubor XML tabulky příkaz.  
  
 [Příkaz konfigurace tabulky (. Soubory CTC)](http://msdn.microsoft.com/en-us/3413dda1-f372-4669-bcf0-c64d3463842c)  
 Obsahuje přehled formátu souboru nepoužívané .ctc.  
  
 [Jak balíčky VSPackages přidávají prvky uživatelského rozhraní](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)  
 Popisuje příkaz specifikace formátu tabulky.  
  
 [Prostředky v balíčcích VSPackage](../../extensibility/internals/resources-in-vspackages.md)  
 Popisuje, jak používat v spravované VSPackages spravovaných a nespravovaných prostředků.  
  
 [Příkazy, nabídky a panely nástrojů](../../extensibility/internals/commands-menus-and-toolbars.md)  
 Vysvětluje, jak vytvářet uživatelské rozhraní, které obsahuje nabídky, panely nástrojů a příkaz pole se seznamem.