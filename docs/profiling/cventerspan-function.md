---
title: Cventerspan – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvEnterSpanVA
- cvmarkers/CvEnterSpanW
- cvmarkers/CvEnterSpanExW
- cvmarkers/CvEnterSpanA
- cvmarkers/CvEnterSpanExVW
- cvmarkers/CvEnterSpanExA
- cvmarkers/CvEnterSpanVW
helpviewer_keywords:
- CvEnterSpanVW method
- CvEnterSpanVA method
- CvEnterSpanExA method
- CvEnterSpanW method
- CvEnterSpanA method
- CvEnterSpanExVW method
- CvEnterSpanExW method
ms.assetid: 91689e9c-6733-44b9-b36a-8b9b2eef7d1d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8d501f7c1e75f5b63c82c34f2dc0a4913d7a88c7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62552629"
---
# <a name="cventerspan-function"></a>Cventerspan – funkce
Označuje začátek toho nové rozpětí.

## <a name="syntax"></a>Syntaxe

```C
HRESULT CvEnterSpanW(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _Out_ PCV_SPAN* ppSpan,
    _In_ PCWSTR pMessage,
    ...
    );

HRESULT CvEnterSpanA(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _Out_ PCV_SPAN* ppSpan,
    _In_ PCSTR pMessage,
    ...
    );

HRESULT CvEnterSpanVW(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _Out_ PCV_SPAN* ppSpan,
    _In_ PCWSTR pMessage,
    _In_ va_list argList
    );

HRESULT CvEnterSpanVA(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _Out_ PCV_SPAN* ppSpan,
    _In_ PCSTR pMessage,
    _In_ va_list argList
    );

HRESULT CvEnterSpanExW(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _In_ CV_IMPORTANCE level,
    _In_ int category,
    _Out_ PCV_SPAN* ppSpan,
    _In_ PCWSTR pMessage,
    ...
    );

HRESULT CvEnterSpanExA(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _In_ CV_IMPORTANCE level,
    _In_ int category,
    _Out_ PCV_SPAN* ppSpan,
    _In_ PCSTR pMessage,
    ...
    );

HRESULT CvEnterSpanExVW(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _In_ CV_IMPORTANCE level,
    _In_ int category,
    _Out_ PCV_SPAN* ppSpan,
    _In_ PCWSTR pMessage,
    _In_ va_list argList);

HRESULT CvEnterSpanExVA(
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,
    _In_ CV_IMPORTANCE level,
    _In_ int category,
    _Out_ PCV_SPAN* ppSpan,
    _In_ PCSTR pMessage,
    _In_ va_list argList);

```

#### <a name="parameters"></a>Parametry
 `argList` Seznam argumentů.

 `category` Kategorie značky span

 `level` Úroveň důležitosti rozpětí.

 `pMarkerSeries` Platné značky řady kontextu. Nemůže mít hodnotu NULL.

 `pMessage` Řetězec formát zprávy. Nemůže mít hodnotu NULL.

 `ppSpan` Adresa proměnné, která bude obsahovat výsledný objekt značky span. Adresa nesmí být NULL, proměnná může mít libovolnou hodnotu.

## <a name="return-value"></a>Návratová hodnota
 S_OK při úspěšném zápisu zprávy. Kód chyby v případě, že došlo k chybám. Použití makra SUCCEEDED nebo FAILED zkontrolujte chybovou podmínku.

## <a name="requirements"></a>Požadavky
 **Header:** *cvmarkers.h*

 **Unicode:** CvEnterSpanW, CvEnterSpanVW, CvEnterSpanExW, CvEnterSpanExVW

 **ANSI:** CvEnterSpanA, CvEnterSpanVA, CvEnterSpanExA, CvEnterSpanExVW

## <a name="see-also"></a>Viz také:
- [Referenční dokumentace knihoven jazyka C++](../profiling/cpp-library-reference.md)