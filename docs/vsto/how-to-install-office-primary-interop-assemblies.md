---
title: 'Postupy: Nainstalovat primární spolupracující sestavení pro Office'
ms.date: 08/14/2019
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- primary interop assemblies [Office development in Visual Studio], installing
- Office primary interop assemblies, installing
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: ee6755a2d795d2018136785986a5a346ddc07dc6
ms.sourcegitcommit: 209ed0fcbb8daa1685e8d6b9a97f3857a4ce1152
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/16/2019
ms.locfileid: "69551790"
---
# <a name="how-to-install-office-primary-interop-assemblies"></a>Postupy: Nainstalovat primární spolupracující sestavení pro Office
  Při instalaci Office nainstalujte systém Microsoft Office primární spolupracující sestavení (PIA).

[!include[Add-ins note](includes/addinsnote.md)]

## <a name="to-install-the-pias-when-you-install-office"></a>Instalace PIA při instalaci Office

1. Ujistěte se, že máte verzi .NET Framework, která není starší než 2,0.

2. Nainstalujte systém Microsoft Office a ujistěte se, že je pro aplikace, které chcete zvětšit, vybraná funkce **Podpora programovatelnosti rozhraní .NET** (Tato funkce je součástí výchozí instalace).

    > [!WARNING]
    > Ve výchozím nastavení jsou ve vašem řešení při sestavování služby PIA vloženy do vašeho řešení, takže nemusíte distribuovat PIA uživatelům jako předpoklady pro používání doplňku VSTO nebo přizpůsobení.

## <a name="see-also"></a>Viz také:
- [Sestavení primární spolupráce pro Office](../vsto/office-primary-interop-assemblies.md)
- [Postupy: Cílové aplikace Office prostřednictvím primárních sestavení spolupráce](../vsto/how-to-target-office-applications-through-primary-interop-assemblies.md)
- [Postupy: Konfigurace počítače pro vývoj řešení pro systém Office](../vsto/how-to-configure-a-computer-to-develop-office-solutions.md)
- [Postupy: Nainstalovat Visual Studio Tools for Office distribuovatelné za běhu](../vsto/how-to-install-the-visual-studio-tools-for-office-runtime-redistributable.md)
- [Přehled &#40;vývoje řešení pro systém Office VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)
- [Začínáme &#40;s vývojem pro Office v sadě Visual Studio&#41;](../vsto/getting-started-office-development-in-visual-studio.md)
