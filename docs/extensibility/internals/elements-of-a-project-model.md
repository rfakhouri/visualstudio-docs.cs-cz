---
title: Prvky modelu projekt | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- projects [Visual Studio SDK], implementation considerations
- project models
- projects [Visual Studio SDK], elements
ms.assetid: a1dbe0dc-68da-45d7-8704-5b43ff7e4fc4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 4933e73df93c1f8a3bcf62e03b6883c0096f1d8f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31135556"
---
# <a name="elements-of-a-project-model"></a>Prvky modelu projektu
Rozhraní a implementace všechny projekty v [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] sdílet základní strukturu: model projektu pro typ vašeho projektu. V projektu modelu, který je VSPackage vyvíjíte, můžete vytvořit objekty, které splňují svoje rozhodnutí o návrhu a fungují společně s globální funkce poskytované službou rozhraní IDE. I když můžete řídit, jak je trvalý položka projektu, například nebudete řídit oznámení, že soubor musí zachovat. Když uživatel umístí fokus na položku otevřít projekt a vybere **Uložit** na **soubor** nabídce [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] nabídky panelu, musí váš kód typ projektu intercept příkazu z prostředí IDE, zachovat soubor, a odešlete oznámení zpět do integrovaného vývojového prostředí už změny souboru.  
  
 Vaše VSPackage komunikuje s IDE prostřednictvím služeb, které poskytují přístup k rozhraní IDE. Prostřednictvím konkrétní služeb, monitorování a trasy například příkazy a zadejte informace o kontextu pro výběr provedené v projektu. Všechny globální IDE funkce potřebné pro vaše VSPackage zajišťuje služby. Další informace o službách najdete v tématu [jak: získat službu](../../extensibility/how-to-get-a-service.md).  
  
 Další aspekty implementace:  
  
-   Model jedné projektu může obsahovat více než jeden typ projektu.  
  
-   Typy projektů a objekty pro vytváření odpovídající projektů jsou registrovány nezávisle identifikátory GUID.  
  
-   Každý projekt, musí mít k souboru šablony nebo průvodce k chybě při inicializaci nový soubor projektu, když uživatel vytvoří nový projekt pomocí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] uživatelského rozhraní. Například [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] šablony inicializovat co přestat soubory .vcproj.  
  
 Následující obrázek znázorňuje primární rozhraní, služeb a objekty, které tvoří implementace typické projektu. Pomocné rutiny aplikace, HierUtil7, můžete použít k vytvoření základní objektů a ostatní programovací standardní. Další informace o pomocné rutiny HierUtil7 aplikací najdete v tématu [není v sestavení: pomocí HierUtil7 projektu třídy k implementaci typu projektu (C++)](http://msdn.microsoft.com/en-us/a5c16a09-94a2-46ef-87b5-35b815e2f346).  
  
 ![Visual Studio projektu modelu grafika](../../extensibility/internals/media/vsprojectmodel.gif "vsProjectModel")  
model projektu  
  
 Další informace o rozhraní a službám uvedeným v předchozím obrázku a dalších volitelné rozhraní nejsou zahrnuty v diagramu najdete v tématu [základní součásti služby projektu modelu](../../extensibility/internals/project-model-core-components.md).  
  
 Projekty může podporovat příkazy a proto musí implementovat <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> rozhraní k účasti ve směrování příkazů prostřednictvím příkazu kontextu identifikátory GUID.  
  
## <a name="see-also"></a>Viz také  
 [Kontrolní seznam: Vytvoření nové typy projektu](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [Není v sestavení: použití HierUtil7 projektu třídy k implementaci typu projektu (C++)](http://msdn.microsoft.com/en-us/a5c16a09-94a2-46ef-87b5-35b815e2f346)   
 [Základní součásti služby projektu modelu](../../extensibility/internals/project-model-core-components.md)   
 [Vytváření instancí projektu pomocí objekty pro vytváření projektů](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)   
 [Postupy: získání služby](../../extensibility/how-to-get-a-service.md)   
 [Vytváření typů projektů](../../extensibility/internals/creating-project-types.md)