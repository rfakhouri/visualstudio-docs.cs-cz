---
title: Karta zprávy, dialogové okno možností zpráv | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: reference
helpviewer_keywords:
- message options, Messages
ms.assetid: fb9fa211-e82c-40a5-9e4b-ba8de07313c0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f19da533d2ab13e7493eae53af8dea3af4e520df
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="messages-tab-message-options-dialog-box"></a>Karta Zprávy, dialogové okno možností zpráv
Použití **zprávy** a vyberte možnost zpráv, které typy v seznamu [zobrazení zpráv](../debugger/messages-view.md)a určení kritérií hledání zpráv. Chcete-li zobrazit [dialogové okno možností zpráv](../debugger/message-options-dialog-box.md), zvolte **zprávy protokolu** z **nástroje Spy** nabídky.  
  
 Obvykle nejprve vybrat **zpráva skupiny**a jejich následné vyladění výběr výběrem jednotlivých **zprávy do zobrazení**. **Všechny** tlačítko vybere všechny typy zpráv a **žádné** tlačítko vymaže všechny typy.  
  
 Následující nastavení jsou k dispozici na **zprávy** karty:  
  
 **Zobrazení zpráv**  
 Vyberte zprávy specifické pro zobrazení. Když vytvoříte nové okno zprávy, zobrazí všechny zprávy. Při filtrování zprávy z **zprávy** kartě Tento filtr platí pouze pro nové zprávy, není zprávy, které již byly zobrazeny v zobrazení oken.  
  
 **Zpráva skupiny**  
 Vyberte skupiny zpráva pro zobrazení. K dispozici skupiny patří:  
  
-   WM_USER: s kódem větší než nebo rovna hodnotě WM_USER  
  
-   Registrované: zaregistrována **RegisterWindowMessage** volání  
  
-   Neznámé: Neznámý zprávy v rozsahu od 0 do (WM_USER - 1)  
  
 Všimněte si, že tyto **zpráva skupiny** nejsou namapovány na konkrétní položky v rámci **zobrazení zpráv**. Když vyberete skupinu, je výběr použitých přímo na datový proud zpráv.  
  
 Šedým zaškrtávací políčko v rámci **zpráva skupiny** znamená, že **zobrazení zpráv** změnil pole se seznamem pro zprávy v dané skupině; jsou vybrány všechny typy zpráv v této skupině.  
  
 **Uložit nastavení jako výchozí**  
 Aktuální nastavení pro pozdější použití uložte jako možnosti vyhledávání zpráv. Tato nastavení jsou také uloženy při ukončení nástroje Spy ++.