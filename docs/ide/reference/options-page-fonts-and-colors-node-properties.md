---
title: Stránka Možnosti, vlastnosti uzlu Písmo a barvy
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- Tools Options settings, Fonts and Colors node properties
- automation [Visual Studio], controlling Tools Options
ms.assetid: 8e1ab784-5f85-4e2b-8ef9-e5d59ca4dbcb
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b5363d71082128c13146c445fe312424be7e4340
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62945591"
---
# <a name="options-page-fonts-and-colors-node-properties"></a>Stránka Možnosti, vlastnosti uzlu Písmo a barvy
Tento dokument popisuje vlastnosti písma a barvy pro panel nástrojů, která je zaregistrovaná a může se zobrazí v rámci **písma a barvy** v **prostředí** kategorii **možnosti** Dialogové okno. Tento atribut podporuje dynamické povaze skupiny, které lze zabarvit položek, které můžete změnit, pokud budou instalovat nebo odinstalovat rozšíření VSPackages.

 Následující část popisuje příklad typ registrované okna a vlastnosti, které jsou k dispozici pro každé okno.

## <a name="text-editor-or-printer-or-dialogs-and-tool-windows"></a>Textový Editor nebo tiskárnu nebo dialogových oken a nástroj pro Windows
 `DTE.Properties("FontsAndColors", "TextEditor")`

 -nebo-

 `DTE.Properties("FontsAndColors", "Printer")`

 -nebo-

 `DTE.Properties("FontsAndColors", "Dialogs and Tool Windows")`

|Název položky vlastnosti|Value|Popis|
| - |-----------|-----------------|
|fontFamily|Získá nebo nastaví (String)|Název písma, které chcete použít, jako je například "New Kurýrní."|
|FontCharacterSet|Získá nebo nastaví (<xref:EnvDTE.vsFontCharSet>)|A <xref:EnvDTE.vsFontCharSet> hodnotu určující typ znakovou sadu, jako je například hebrejština nebo ruština.|
|Velikost písma|Získá nebo nastaví (krátký)|Velikost písma pro použití v bodech. Například 10 nebo 12.|

## <a name="see-also"></a>Viz také

- [Řízení nastavení možností](https://msdn.microsoft.com/Library/a09ed242-7494-4cde-bbd1-7a8ec617965d)
- [Určování názvů položky vlastností na stránkách možností](https://msdn.microsoft.com/Library/d450422d-47c7-4eeb-9f9f-3286264bc5aa)
- [Stránka Možnosti, vlastnosti uzlu Prostředí](../../ide/reference/options-page-environment-node-properties.md)
- [Stránka Možnosti, vlastnosti uzlu Textový editor](../../ide/reference/options-page-text-editor-node-properties.md)