---
title: Automatizace pro konfiguraci a objekty SelectedItem | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- automation [Visual Studio SDK], SelectedItem object
- automation [Visual Studio SDK], builds
ms.assetid: 120377f1-51aa-4445-b2f7-06ab7fc2b47f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1ee4bcddd7c23f5178984c2c76b059209a965956
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/18/2019
ms.locfileid: "56335334"
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