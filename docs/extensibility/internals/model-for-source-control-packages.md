---
title: "Pro zdroj ovládacího prvku balíčky | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- source control [Visual Studio SDK], model
ms.assetid: 6164b2d3-a622-4de8-bef3-a6de985e9ebd
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 1960b5fe7b7c507b5b3275315ea6ae1715c27f76
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="model-for-source-control-packages"></a>Model pro balíčky zdroj ovládacího prvku
Následující model představuje příklad implementace ovládacího prvku zdroje. V modelu uvidíte rozhraní, které je nutné implementovat a prostředí služby, které je třeba volat. Všechny služby, jako je ve skutečnosti volání metody určité rozhraní, které jste získali mimo službu. Aby bylo snazší zjistit, jak se provádí kontrola zdroje jsou identifikovány názvy tříd.  
  
 ![SCC &#95; Příklady TUP](../../extensibility/internals/media/scc_tup.gif "SCC_TUP –")  
Příklad zdroj řízení projektu  
  
## <a name="interfaces"></a>Rozhraní  
 Správa zdrojového kódu můžete implementovat pro vaši nové typy projektů v sadě Visual Studio pomocí seznamu rozhraní, které jsou uvedené v následující tabulce.  
  
|Rozhraní|Použití|  
|---------------|---------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>|Voláno rozhraním projekty a editory před jejich uložení nebo změnu (dirty) soubory. Toto rozhraní je možné získat pomocí <xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave> služby.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>|Volá projekty tak, aby žádala o oprávnění k přidání, odebrání nebo přejmenujte soubor nebo adresář. Toto rozhraní je také označován projekty informovat, že prostředí při schválené přidat, odebrat nebo přejmenovat akce je dokončena. Je přístupný pomocí <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments> služby.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>|Každá entita, která registruje oznámení o přidání projekty implementované, přejmenujte nebo odeberte soubor nebo adresář. Registrace pro oznámení o události, volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2.AdviseTrackProjectDocumentsEvents%2A>.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>|Voláno rozhraním projekty pro registraci s zdrojový balíček řízení a získat informace o řízení stav zdroje. Toto rozhraní je možné získat pomocí <xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager> služby.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>|Implementované projektu reagovat na požadavky řízení zdroje informace o souborech a získat zdroj nastavení řízení nezbytný pro soubor projektu.|  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2.AdviseTrackProjectDocumentsEvents%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>   
 [Podpora správy zdrojového kódu](../../extensibility/internals/supporting-source-control.md)