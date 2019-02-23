---
title: Karta zprávy, dialogové okno možností zpráv | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- message options, Messages
ms.assetid: fb9fa211-e82c-40a5-9e4b-ba8de07313c0
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: de50e6fe997ce10266cbb51f2fd91c318ab2bd1f
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/22/2019
ms.locfileid: "56681293"
---
# <a name="messages-tab-message-options-dialog-box"></a>Karta Zprávy, dialogové okno možností zpráv
Použití **zprávy** kartu, vyberte v seznamu typů zpráv, které [zobrazení zpráv](../debugger/messages-view.md)a určení kritérií hledání zpráv. Chcete-li zobrazit [dialogové okno možností zpráv](../debugger/message-options-dialog-box.md), zvolte **zprávy protokolu** z **Spy** nabídky.

 Obvykle nejprve vybrat **skupiny zpráv**a poté doladit tak, že vyberete jednotlivé výběr **zprávy do zobrazení**. **Všechny** tlačítko vybere všechny typy zpráv a **žádný** tlačítko zruší výběr všech typů.

 Následující nastavení jsou k dispozici na **zprávy** kartu:

 **Zprávy do zobrazení** vyberte konkrétní zprávy pro zobrazení. Při vytváření nové okno zprávy může zobrazit všechny zprávy. Při filtrování zpráv **zprávy** kartu, tento filtr platí jenom pro nové zprávy, ne zprávy, které již byly zobrazeny v zobrazení Windows.

 **Zpráva skupiny** vybrat skupiny zprávy pro zobrazení. Dostupné skupiny patří:

- WM_USER: s kódem větší než nebo rovna hodnotě WM_USER

- Registrovaný: zaregistrované **RegisterWindowMessage** volání

- Neznámé: neznámé zprávy v rozsahu 0 až (WM_USER - 1)

  Všimněte si, že tyto **skupiny zpráv** nelze namapovat na konkrétní položky v rámci **zobrazení zpráv**. Když vyberete skupinu, je výběr použitých přímo na datové proudy zpráv.

  Šedým zaškrtávací políčko v rámci **skupiny zpráv** znamená, že **zobrazení zpráv** se změnila pole se seznamem pro zprávy v dané skupině; jsou vybrány všechny typy zpráv v této skupině.

  **Uložit nastavení jako výchozí** uložit aktuální nastavení pro pozdější použití jako možnosti hledání zpráv. Tato nastavení jsou také uloženy při ukončení nástroje Spy ++.