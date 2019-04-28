---
title: Omezení délky řetězců | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, restrictions on string lengths
ms.assetid: 877173d2-ca27-43b3-b1f4-8379f7c5e268
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8ade5e9ac188cd6c1b721ed276e0c4e2aff71f32
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63434737"
---
# <a name="restrictions-on-string-lengths"></a>Omezení délky řetězců
Rozhraní API modulu Plug-in zdroje ovládacího prvku omezení délky řetězce použité v různých funkcí.

## <a name="string-length-values"></a>Hodnoty pro délku řetězce

|Konstanta|Hodnota|
|--------------|-----------|
|`SCC_NAME_LEN`|31|
|`SCC_AUXLABEL_LEN`|31|
|`SCC_USER_LEN`|31|
|`SCC_PRJPATH_LEN`|300|

> [!NOTE]
> Délka nezahrnuje ukončení `null`. Další konstantám s příponou "_velikost" místo "_LEN" zahrnout místa pro ukončení `null`.

|Konstanta|Value|
|--------------|-----------|
|SCC_NAME_SIZE|32|
|SCC_AUXLABEL_SIZE|32|
|SCC_USER_SIZE|32|
|SCC_PRJPATH_SIZE|301|

## <a name="see-also"></a>Viz také:
- [Ovládací prvek moduly plug-in zdrojového kódu](../extensibility/source-control-plug-ins.md)