---
title: Implementace dodavatele portu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], implementing port suppliers
- port suppliers, implementing
ms.assetid: 6b8579df-58df-4c7f-8112-6015993e8765
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5d6875baf72d94494a1abaea9260e344b236f83c
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62925582"
---
# <a name="implement-a-port-supplier"></a>Implementace dodavatele portu
Dodavatele portu poskytuje porty na požadavek na správce ladění relace (SDM). Při ladění k počítači bez modelu DCOM nebo když nová zařízení vyžaduje podporu, musí být implementované dodavatele portu. Například k poskytování ladění na mobilní telefon, může být nastavíte dodavatele portu, který poskytuje porty, které slouží k připojení k mobilní telefon (například prostřednictvím prostředí IR nebo buňky připojení) a vytváří výčet procesů a programy spuštěné na telefonu.

 Ladění programů na počítače se systémem Windows (včetně vzdáleného ladění) Visual Studio poskytuje dodavatelé portů pro nativní a procesy Common Language Runtime (CLR), takže není nutné nastavit vlastní dodavatele portu v těchto případech.

## <a name="in-this-section"></a>V tomto oddílu
 [Implementace a registrace dodavatele portu](../../extensibility/debugger/implementing-and-registering-a-port-supplier.md) popisuje, jak SDM komunikuje s dodavatele portu a jeho porty.

 [Požadovaná rozhraní dodavatele portu](../../extensibility/debugger/required-port-supplier-interfaces.md) dokumenty rozhraní, je nutné implementovat zobrazíte dodavatele portu.

## <a name="related-sections"></a>Související oddíly
 [Koncepty ladicího programu](../../extensibility/debugger/debugger-concepts.md) popisuje hlavní koncepty ladění architektury.

## <a name="see-also"></a>Viz také:
 [Rozšiřitelnost ladicího programu Visual Studio](../../extensibility/debugger/visual-studio-debugger-extensibility.md)