---
title: Model pro balíčky správy zdrojového kódu | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], model
ms.assetid: 6164b2d3-a622-4de8-bef3-a6de985e9ebd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1ad60503c9f7b15bd4665fb8f9552864debc381d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62909199"
---
# <a name="model-for-source-control-packages"></a>Model pro balíčky správy zdrojového kódu
Následující model představuje příklad implementace ovládacího prvku zdroje. V modelu uvidíte, které musí implementovat rozhraní a prostředí služby, které je nutné volat. Stejně jako všechny služby ve skutečnosti volat metody určité rozhraní, který získáte mimo jiné služby. Aby bylo snazší zjistit, jak se provádí správy zdrojového kódu se identifikují názvy tříd.

 ![SCC&#95;TUP příklady](../../extensibility/internals/media/scc_tup.gif "SCC_TUP –") projektu ve správě zdrojového příklad

## <a name="interfaces"></a>Rozhraní
 Správy zdrojového kódu můžete implementovat pro vaši nových typů projektů v sadě Visual Studio pomocí seznam rozhraní, které jsou uvedeny v následující tabulce.

|Rozhraní|Použití|
|---------------|---------|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>|Volá se, projekty a editory před jejich uložit nebo soubory změnu (změny). Toto rozhraní se přistupuje pomocí <xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave> služby.|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>|Je voláno projekty můžete požádat o oprávnění, které chcete přidat, odebrat nebo přejmenovat soubor nebo adresář. Toto rozhraní se také nazývá projekty informovat, že je kompletní prostředí, když se schválené přidat, odebrat nebo přejmenovat akce. Přistupuje se k němu pomocí <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments> služby.|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>|Každá entita, která registruje upozornění, až projekty přidání, přejmenování nebo odstranění souboru nebo adresáře implementované. Chcete-li zaregistrovat pro oznámení události, zavolejte <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2.AdviseTrackProjectDocumentsEvents%2A>.|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>|Je voláno projekty k registraci balíčku ovládací prvek zdroje a získat informace o stav správy zdrojových kódů. Toto rozhraní se přistupuje pomocí <xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager> služby.|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>|Implementovaná tímto projektem reagovat na požadavky řízení zdrojové informace o souborech a získat zdroj nastavení nezbytný pro soubor projektu.|

## <a name="see-also"></a>Viz také
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2.AdviseTrackProjectDocumentsEvents%2A>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>
- [Podpora správy zdrojového kódu](../../extensibility/internals/supporting-source-control.md)