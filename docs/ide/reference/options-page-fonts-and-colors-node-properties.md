---
title: "Stránka Možnosti, písma a barvy vlastnosti uzlu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Tools Options settings, Fonts and Colors node properties
- automation [Visual Studio], controlling Tools Options
ms.assetid: 8e1ab784-5f85-4e2b-8ef9-e5d59ca4dbcb
caps.latest.revision: "8"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 0c2618dbaad3fcae95219e2b6a8a1f9b3d87bf09
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="options-page-fonts-and-colors-node-properties"></a>Stránka Možnosti, vlastnosti uzlu Písmo a barvy
Tento dokument popisuje vlastnosti písma a barev pro okno nástroje, které je registrované k vyskytovat v části **písma a barev** v **prostředí** kategorii **možnosti** Dialogové okno. To podporuje dynamické povaha skupiny colorable položek, které můžete změnit, pokud jsou VSPackages nainstalována nebo odinstalována.  
  
 V následující části je příkladem okno registrovaný typ a vlastnosti, které jsou k dispozici pro každé okno.  
  
## <a name="text-editor-or-printer-or-dialogs-and-tool-windows"></a>Textového editoru nebo tiskárny nebo dialogová okna a nástroje systému Windows  
 `DTE.Properties("FontsAndColors", "TextEditor")`  
  
 -nebo-  
  
 `DTE.Properties("FontsAndColors", "Printer")`  
  
 -nebo-  
  
 `DTE.Properties("FontsAndColors", "Dialogs and Tool Windows")`  
  
|Název položky vlastnosti|Hodnota|Popis|  
|------------------------|-----------|-----------------|  
|FontFamily|Get/Set (String)|Název písma, který chcete použít, například "Nové Kurýrní."|  
|FontCharacterSet|Get/Set (<xref:EnvDTE.vsFontCharSet>)|A <xref:EnvDTE.vsFontCharSet> hodnotu, určení typu znakovou sadu chcete použít, například hebrejština nebo ruština.|  
|Velikost písma|Get/Set (krátký)|Velikost písma pro použití v bodech. Například 10 a 12.|  
  
## <a name="see-also"></a>Viz také  
 [Ovládání možnosti nastavení](http://msdn.microsoft.com/Library/a09ed242-7494-4cde-bbd1-7a8ec617965d)   
 [Určení názvů vlastností položky na stránkách možnosti](http://msdn.microsoft.com/Library/d450422d-47c7-4eeb-9f9f-3286264bc5aa)   
 [Stránka Možnosti, vlastnosti uzlu prostředí](../../ide/reference/options-page-environment-node-properties.md)   
 [Stránka Možnosti, vlastnosti uzlu textového editoru](../../ide/reference/options-page-text-editor-node-properties.md)