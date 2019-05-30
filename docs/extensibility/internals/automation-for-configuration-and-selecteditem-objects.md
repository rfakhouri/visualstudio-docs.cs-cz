---
title: Automatizace pro konfiguraci a objekty SelectedItem | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- automation [Visual Studio SDK], SelectedItem object
- automation [Visual Studio SDK], builds
ms.assetid: 120377f1-51aa-4445-b2f7-06ab7fc2b47f
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e6c9dc8012433f9ec73f15b9249f6b7ac08bdad7
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66347977"
---
# <a name="automation-for-configuration-and-selecteditem-objects"></a>Automatizace pro objekty konfigurace a SelectedItem

Můžete automatizovat sestavení a procesy pro vybranou položku v sadě Visual Studio.

## <a name="automation-for-builds"></a>Automatizace pro sestavení

Sestavení nebo konfigurace má modelu automatizace, který je k dispozici při implementaci <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider>. Další informace najdete v tématu [pochopení konfigurace sestavení](../../ide/understanding-build-configurations.md).

Pokud vytvoříte VSPackage a chcete mít pod kontrolou možnosti konfigurace, musíte použít model automatizace.

## <a name="automation-for-selecteditem"></a>Automatizace pro SelectedItem

Není nutné poskytnout implementaci pro `SelectedItem` objektu, protože Visual Studio obsahuje standardní implementace. Ale můžete implementovat `SelectedItem` objektu, pokud dáváte přednost. Musí implementovat objekt, který obsahuje `SelectedItem` rozhraní a vrátí odpověď na volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A> metodu s `VSITEMID` nastavena na [__VSHPROPID. VSHPROPID_ExtSelectedItem](<xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID.VSHPROPID_ExtSelectedItem>).

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A>
- [Přispívání do modelu automatizace](../../extensibility/internals/contributing-to-the-automation-model.md)
- [Principy konfigurací sestavení](../../ide/understanding-build-configurations.md)