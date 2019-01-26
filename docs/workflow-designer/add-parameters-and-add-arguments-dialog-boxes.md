---
title: Návrhář postupu provádění - přidat parametry a přidat argumenty dialogových oknech
ms.date: 11/04/2016
ms.topic: reference
ms.prod: visual-studio-dev15
f1_keywords:
- AddParameters.UI
ms.assetid: a21fb4fe-134b-40b0-8497-86b842940ca1
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 9c9fae97c3a7dbd59eceea6fd5876005cfaee128
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54995046"
---
# <a name="add-parameters-and-add-arguments-dialog-boxes"></a>Dialogová okna Přidat parametry a Přidat argumenty

Následující tabulka popisuje prvky uživatelského rozhraní (UI) **přidat parametry** dialogové okno používané <xref:System.Activities.Statements.InvokeMethod> návrháře:

|||
|-|-|
|**Směr**|Určuje, zda parametr představuje tok dat do metody mimo metodu, nebo obojí.|
|**Typ**|Název typu nový parametr.|
|**Hodnota**|Výraz jazyka Visual Basic, kterého chcete přiřadit nový parametr výchozí hodnotu|

Následující tabulka popisuje prvky uživatelského rozhraní (UI) **Přidat argumenty** dialogové okno používané <xref:System.Activities.Statements.InvokeDelegate> návrháře:

|||
|-|-|
|**Název**|Název argumentu.|
|**Směr**|Určuje, zda argument představuje tok dat do delegáta z delegáta nebo obojí.|
|**Typ**|Název typu argumentu nové.|
|**Hodnota**|Hodnota se použije pro tuto instanci argument delegáta.|