---
title: Zdroj modulu Runtime podrobnosti ovládacího prvku | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], runtime details
ms.assetid: 1acd30e0-f98c-4bde-b9cd-4076845887df
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 0bb52770557fa37a14040b686dcdfbf345a713a2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68183371"
---
# <a name="source-control-runtime-details"></a>Podrobnosti modulu CLR správy zdrojového kódu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Projekt je přidán do správy zdrojového kódu, když uživatel přidá soubor v projektu do správy zdrojových kódů, nebo prostřednictvím kontrolér automatizace, jako je průvodce. Projekt neurčuje sama za sebe, že je pod správou zdrojových kódů; podporuje správy zdrojových kódů, ale je nutné přidat do něj ručně.  
  
## <a name="registering-with-a-source-control-package"></a>Registrace balíčku zdrojového ovládacího prvku  
 Když soubor v projektu se přidá do správy zdrojových kódů, prostředí volá <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2.SetSccLocation%2A> poskytnout čtyři neprůhledné řetězce, které jsou používány systém správy zdrojového kódu jako soubory cookie. Store tyto řetězce v souboru projektu. Tyto řetězce by měly být předány zdrojového ovládacího prvku se zakázaným inzerováním (součást sady Visual Studio, který spravuje balíčky správy zdrojového kódu) při spuštění projektu typu při volání <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.RegisterSccProject%2A>. To pak načte balíček příslušný zdrojový ovládací prvek a předává volání jeho implementace `IVsSccManager2::RegisterSccProject`.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.RegisterSccProject%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2.SetSccLocation%2A>   
 [Podpora správy zdrojového kódu](../../extensibility/internals/supporting-source-control.md)
