---
title: Typ Vizualizéru a vlastní prohlížeč | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], custom viewer
- debugging [Debugging SDK], type visualizer
ms.assetid: fd3691e6-9c78-4767-846f-43f85ada4375
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 219632bce50b6942d46e4061a3c7eaf8f70adfd5
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62864239"
---
# <a name="type-visualizer-and-custom-viewer"></a>Vizualizér typů a vlastní prohlížeč
Typ vizualizéru je komponenta, která zobrazuje část dat v určitém formátu. Formát je zcela až který implementuje vizualizéru, už to koncového uživatele nebo jiného dodavatele vizualizéry.

 Vlastní prohlížeč je součástí Chyba při vyhodnocování vlastní výraz, který zobrazuje část dat v určitém formátu. Tento formát je zcela v kompetenci implementátora vlastní prohlížeč, což znamená, že formát až implementátora vyhodnocovací filtr výrazů (EE).

## <a name="support-for-type-visualizers-in-an-expression-evaluator"></a>Podpora pro vizualizérů typů v vyhodnocovače výrazů
 EE podporuje vizualizérů typů podporuje sadu rozhraní, které jsou přístupné pro vizualizátory: rozhraní, jako například [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md) a [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md). Ale EE nezodpovídá za implementace vizualizér typů samotné: EE pouze umožňuje vizualizéry externí přístup k jeho informace o typu. Takové vizualizéry může dodávaná EE a nainstalovaný na příslušné místo v sadě Visual Studio, zadán pomocí jiného dodavatele třetích stran nebo dokonce koncovým uživatelem.

## <a name="support-for-custom-viewers-in-an-expression-evaluator"></a>Podpora vlastních prohlížečů v vyhodnocovače výrazů
 EE může také podporovat vlastních prohlížečů, ve kterých EE samotné poskytuje kód pro zobrazení datového typu. Implementuje vlastní prohlížeč [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md) požadované rozhraní, která zpracovává všechny úkoly zobrazovat data v libovolné formát; prohlížeč má plnou kontrolu nad zobrazením a dokonce můžete nechat data upravit. Žádné vlastních prohlížečů poskytovaných EE jsou dostupné EE při dodání produktu.

## <a name="see-also"></a>Viz také:
- [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md)
- [Chyba při vyhodnocování výrazu](../../extensibility/debugger/expression-evaluator.md)
- [Ladicí stroj](../../extensibility/debugger/debug-engine.md)
- [IDebugCustomViewer](../../extensibility/debugger/reference/idebugcustomviewer.md)
- [IEEVisualizerService](../../extensibility/debugger/reference/ieevisualizerservice.md)
- [IEEVisualizerDataProvider](../../extensibility/debugger/reference/ieevisualizerdataprovider.md)