---
title: Upravit a pokračovat není podporována pro F# | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue [F#]
- Debugging [F#], Edit and Continue
ms.assetid: 40ec77bb-07e3-4b58-9254-ae015009441c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ceb0ca767b1ac6364e103925fb86ed639c3d321d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62851161"
---
# <a name="edit-and-continue-not-supported-for-f"></a>Operace Upravit a pokračovat není podporována pro F#. #
Upravit a pokračovat není podporovaná při ladění F# kódu. Úpravy F# kódu je možné během relace ladění, ale mělo by se vyhnout. Během relace ladění se nepoužijí změny kódu. Proto se veškeré úpravy provedené F# kódu během ladění způsobí zdrojový kód, který neodpovídá kódu, který se právě ladí.
