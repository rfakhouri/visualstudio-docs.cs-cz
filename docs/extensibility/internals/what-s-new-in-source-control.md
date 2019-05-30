---
title: Co je nového ve správě zdrojového kódu v aplikaci Visual Studio 2015 SDK | Dokumentace Microsoftu
titleSuffix: ''
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- what's new [Visual Studio SDK], source control
- source control [Visual Studio SDK], what's new
ms.assetid: bcf85418-18fb-4824-9dae-d14bf3d56a77
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: e12776c21d345d60992eeff4963498bcd7d56678
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/29/2019
ms.locfileid: "66323255"
---
# <a name="whats-new-in-source-control-for-the-visual-studio-2015-sdk"></a>Co je nového ve správě zdrojového kódu pro Visual Studio 2015 SDK

V [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)], může nabídnout řešení hluboce integrované zdrojového ovládacího prvku implementací balíčku VSPackage správy zdrojového kódu. Tato část popisuje funkce správy zdrojového kódu rozšíření VSPackages a poskytuje přehled o implementaci.

## <a name="the-source-control-vspackage"></a>Ovládací prvek VSPackage zdroje

Visual Studio podporuje dva druhy řešení pro řízení zdrojů. Ve všech verzích aplikace Visual Studio, můžete stále integrovat na rozhraní API modulu Plug-in zdroje ovládacího prvku modulu plug-in. Můžete také vytvořit VSPackage pro správu zdrojového kódu, který poskytuje hluboká integrace, [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] vhodná pro řešení pro řízení zdrojů, které vyžadují vysokou úroveň vyspělosti a autonomie cestu.

VSPackage můžete přidat téměř libovolný typ funkce se sadou Visual Studio. Balíčku VSPackage správy zdrojového kódu poskytuje funkci úplný zdrojový ovládací prvek pro Visual Studio, v uživatelském rozhraní zobrazovat uživateli back-end odpovíte na sdělení a systém správy zdrojového kódu.

Implementace balíčku VSPackage správy zdrojového kódu vyžaduje strategii "všechno nebo nic". Tvůrce balíčku VSPackage správy zdrojového kódu musí investovat značné úsilí při implementaci řady rozhraní ovládacího prvku zdroje a nových prvků uživatelského rozhraní (dialogová okna, nabídek a panelů nástrojů) k pokrytí celé funkce správy zdrojového kódu, a také rozhraní budete muset všechny balíčku úspěšně integrace pomocí sady Visual Studio.

Následující kroky poskytují obecný přehled toho, co je potřeba implementovat zdrojový balíček ovládacího prvku. Podrobnosti najdete v tématu [vytváření VSPackage ovládací prvek zdroje](../../extensibility/internals/creating-a-source-control-vspackage.md).

1. Vytvoření VSPackage proffers službu správy privátní zdrojových kódů.

2. Implementovat rozhraní související s ovládacími služeb zdroje, které jsou proffered pomocí sady Visual Studio (například <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2> a <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider> rozhraní).

3. Registrace správy zdrojového kódu VSPackage.

4. Implementujte všechny správy zdrojového kódu uživatelského rozhraní, včetně položek nabídky, dialogová okna, panely nástrojů a kontextové nabídky.

5. Všechny zdroje události související s ovládacími jsou předány do správy zdrojových kódů VSackage, když je aktivní a musí být zpracována vaše VSPackage.

6. Správy zdrojového kódu VSPackage musí naslouchat událostem ohrožují implementující <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3> rozhraní a sledování projektu dokumentu (TPD) události (jak je implementované <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> rozhraní) a proveďte potřebné akce.

## <a name="see-also"></a>Viz také:

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>
- [Přehled](../../extensibility/internals/source-control-integration-overview.md)
- [Vytvoření balíčku VSPackage správy zdrojového kódu](../../extensibility/internals/creating-a-source-control-vspackage.md)