---
title: Iwefdebuggingsupport – rozhraní
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: a71adf5371275fbbdc19cdf09be96ef900ec073d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62583760"
---
# <a name="iwefdebuggingsupport-interface"></a>Iwefdebuggingsupport – rozhraní
  Implementované ladicí prostředí, jako je Visual Studio, k usnadnění ladění aplikací pro Office. Aplikace Office, jako je například aplikaci Word nebo Excel, získá tato rozhraní ze sady Visual Studio a potom zavolá metody na rozhraní v určitých bodech během relace ladění.

## <a name="syntax"></a>Syntaxe

```csharp
[
    uuid(ccaf1a90-ce1c-4199-9cd6-b40c5c57a671),
    oleautomation
]
interface IWefDebuggingSupport : IUnknown
{
    HRESULT SetWefProcessId(
        [in] DWORD dwProcessId);
    HRESULT GetAutoInsertExtensions(
        [out, retval] SAFEARRAY(BSTR)* psaExtensionNames);
}
```

## <a name="methods"></a>Metody
 Následující tabulka uvádí metody, které definuje iwefdebuggingsupport – rozhraní.

|Název|Popis|
|----------|-----------------|
|[Getautoinsertextensions – metoda](../vsto/getautoinsertextensions-method.md)|Získá informace o aplikacích pro Office, které se mají automaticky vložit během ladění.|
|[Setwefprocessid – metoda](../vsto/setwefprocessid-method.md)|Poskytuje identifikátor procesu, který se spustí rozšíření webové rozhraní Framework (WEF) obsah.|
