---
title: Struktura balíčku VSPackage (řízení zdrojového balíčku VSPackage) | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, structure
- source control packages, VSPackage overview
ms.assetid: 92722be7-b397-48c3-a7a7-0b931a341961
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 03b9d4fb6a92694df55d6732ac80d75645209a87
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/22/2019
ms.locfileid: "60071275"
---
# <a name="vspackage-structure-source-control-vspackage"></a>Struktura balíčku VSPackage (balíček VSPackage správy zdrojového kódu)

Zdrojový ovládací prvek balíčku SDK poskytuje pokyny pro vytvoření VSPackage, která umožňují implementátora ovládacího prvku zdroj integrovat funkce správy zdrojového kódu své prostředí sady Visual Studio. VSPackage je komponenta modelu COM, který je obvykle načtena na vyžádání pomocí integrovaného vývojového prostředí (IDE) sady Visual Studio na základě služeb, které mají být inzerovány balíček v jeho položky registru. Musí implementovat všechny VSPackage <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>. VSPackage obvykle využívá služeb, které Visual Studio IDE a proffers některých služeb.

VSPackage deklaruje jeho položky nabídky a vytvoří výchozí položku Stav prostřednictvím souboru .vsct. Integrovaném vývojovém prostředí sady Visual Studio zobrazí položky nabídky v tomto stavu, dokud nebude vložen sady VSPackage. Následně sady VSPackage provádění <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metoda je volána k povolení nebo zakázání položky nabídky.

## <a name="source-control-package-characteristics"></a>Vlastnosti balíčku zdrojového ovládacího prvku

Balíčku VSPackage správy zdrojového kódu je integrováno do sady Visual Studio. Sémantika VSPackage patří:

- Rozhraní k implementaci tím, že se VSPackage ( `IVsPackage` rozhraní)

- Implementace příkazu uživatelského rozhraní (.vsct souborů a provádění <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní)

- Registrace balíčku VSPackage pomocí sady Visual Studio.

Ovládací prvek zdroje balíčku VSPackage musí komunikovat s tyto sady Visual Studio entity:

- Projekty

- Editory

- Řešení

- Windows

- Spuštění tabulky dokumentů

### <a name="visual-studio-environment-services-that-may-be-consumed"></a>Prostředí služby Visual Studio, které mohou být využívány

<xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>

<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>

<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>

SVsRegisterScciProvider Service

<xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave>

<xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>

<xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager>

### <a name="vsip-interfaces-implemented-and-called"></a>Rozhraní VSIP implementovat a s názvem

Zdrojový ovládací prvek balíček je VSPackage, a proto mohou komunikovat přímo s další rozšíření VSPackages, které jsou registrované pomocí sady Visual Studio. Pokud chcete zajistit plnou škálu funkce správy zdrojového kódu, můžete řešení správy zdrojového kódu VSPackage s rozhraním poskytovaným tímto systémem projektů nebo prostředí.

Každý projekt v sadě Visual Studio musí implementovat <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3> Chcete-li rozpoznán jako projekt v integrovaném vývojovém prostředí sady Visual Studio. Však není toto rozhraní specializované dostatečná pro správu zdrojového kódu. Implementace řídit projekty, které se očekává, že se v části zdroj <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>. Toto rozhraní je používán ovládací prvek zdroje balíčku VSPackage dotazy projekt pro jeho obsah a poskytnout ho glyfy a informace o vazbě (informace potřebné k navázání připojení mezi umístěním serveru a na místo na disku, který je v rámci projektu správy zdrojového kódu).

Ovládací prvek zdroje balíčku VSPackage implementuje <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>, který zase umožňuje zaregistrovat pro správu zdrojového kódu a jejich stav glyfy načítat projekty.

Úplný seznam rozhraní, které musíte zvážit balíčku VSPackage správy zdrojového kódu, naleznete v tématu [související služby a rozhraní](../../extensibility/internals/related-services-and-interfaces-source-control-vspackage.md).

## <a name="see-also"></a>Viz také:

- [Prvky návrhu](../../extensibility/internals/source-control-vspackage-design-elements.md)
- [Související služby a rozhraní](../../extensibility/internals/related-services-and-interfaces-source-control-vspackage.md)