---
title: Uživatelské rozhraní vlastností projektu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project properties [Visual Studio], user interface
- projects [Visual Studio SDK], properties UI
- project properties UI
ms.assetid: b6aec634-8533-476c-9ebd-36536a2288e2
caps.latest.revision: 17
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 31840c40f2a494ffd32f5241e2770938138877e9
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/15/2019
ms.locfileid: "65704089"
---
# <a name="project-property-user-interface"></a>Uživatelské rozhraní vlastností projektu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Podtyp projektu pomocí položek v projektu **stránky vlastností** dialogové okno poskytnuté základního projektu, skrýt nebo dodávaný vytvořit ovládací prvky jen pro čtení a celé stránky nebo přidání stránek specifických pro podtyp projektu **Stránky vlastností** dialogové okno.  
  
## <a name="extending-the-project-property-dialog-box"></a>Rozšíření dialogové okno vlastností projektu  
 Podtyp projektu implementuje rozšiřující objekty automatizace a objekty procházet konfigurace projektu. Implementace těchto zařízení Extender <xref:EnvDTE.IFilterProperties> rozhraní provést určité vlastnosti, skrytá nebo jen pro čtení. **Stránky vlastností** dialogové okno základního projektu, implementovaných základní projekt respektuje filtrování prováděné zařízení Extender automatizace.  
  
 Součástí procesu rozšíření **vlastnost projektu** dialogové okno je popsaný níže:  
  
- Základní projekt načte rozšiřujících objektů z podtyp projektu implementací <xref:EnvDTE80.IInternalExtenderProvider> rozhraní. Toto rozhraní implementují procházet, automatizace projektu a procházet objekty konfigurace projektu všechny základního projektu.  
  
- Provádění <xref:EnvDTE80.IInternalExtenderProvider> pro objekt procházení projektu a projekt automatizační objekt delegovat <xref:EnvDTE80.IInternalExtenderProvider> provádění agregátoru podtyp projektu (to znamená, že `QueryInterface` pro <xref:EnvDTE80.IInternalExtenderProvider> na <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> objekt projektu).  
  
- Objekt konfigurace procházet základní projektu také implementuje <xref:EnvDTE80.IInternalExtenderProvider> propojí přímo v zařízení Extender automatizace z objektu konfigurace podtyp projektu. Jeho implementace delegoval vůči <xref:EnvDTE80.IInternalExtenderProvider> rozhraní implementované agregátoru podtyp projektu.  
  
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject.GetProjectItem%2A>, implementované procházet objekt konfigurace projektu, vrátí <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> objektu.  
  
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgBrowseObject.GetCfg%2A>, také implementováno pomocí procházení objekt konfigurace projektu, vrátí <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfg> objektu.  
  
- Podtyp projektu můžete určit odpovídající identifikátory CatID pro různé objekty Dal základního projektu za běhu načtením následujících <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2> hodnoty:  
  
  - <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>  
  
  - <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>  
  
  - <xref:Microsoft.VisualStudio.Shell.Interop.__VSHPROPID2>  
  
  Pokud chcete zjistit identifikátory CatID pro rozsahu projektu, načte podtyp projektu výše uvedené vlastnosti pro <xref:Microsoft.VisualStudio.VSConstants.VSITEMID> z `VSITEMID``typedef`. Podtyp projektu může být také vhodné určit, které **stránky vlastností** stránek dialogového okna se zobrazí pro projekt, závislé na konfiguraci a konfigurace, které jsou nezávislé. Některé podtypů projektů mohou muset odebrat integrované stránky a přidat konkrétní stránky podtyp projektu. Chcete-li povolit toto volání klienta spravovaného projektu <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy.GetProperty%2A> metoda pro následující vlastnosti:  
  
- `VSHPROPID_PropertyPagesCLSIDList` – seznam oddělený středníkem CLSID stránky vlastností nezávislé na konfiguraci.  
  
- `VSHPROPID_CfgPropertyPagesCLSIDList —` středníkem oddělený seznam CLSID stránky vlastností závislé na konfiguraci.  
  
  Vzhledem k tomu, že projekt podtypu agregace <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> objektu, jej můžete přepsat definice těchto vlastností lze určit, které **stránky vlastností** dialogová okna se zobrazí. Podtyp projektu můžete načíst tyto vlastnosti z vnitřní základního projektu a pak přidat nebo odebrat CLSID podle potřeby.  
  
  Nové stránky vlastností přidal podtyp projektu se předá objekt procházet konfigurace projektu z implementací základní projekt. Tento objekt procházet konfigurace projektu podporuje zařízení Extender automatizace. Další informace o AutomationExtenders najdete v tématu [implementace a rozšiřující objekty pomocí](https://msdn.microsoft.com/library/0d5c218c-f412-4b28-ab0c-33a611f62356). Na stránkách vlastností, které implementují volání podtyp projektu <xref:EnvDTE.Project.Extender%2A> načíst vlastní projekt podtyp procházet objekt konfigurace, která rozšiřuje objekt procházet konfigurace základního projektu.  
  
## <a name="see-also"></a>Viz také  
 <xref:EnvDTE.IFilterProperties>   
 [Dialogové okno stránky vlastností](https://msdn.microsoft.com/4a3d34ac-ed03-45e8-ae60-a0e1aad300e4)
