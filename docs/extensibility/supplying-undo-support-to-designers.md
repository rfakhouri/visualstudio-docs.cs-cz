---
title: "Poskytnutí vrátit zpět na podporu, aby návrháři | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: designers [Visual Studio SDK], undo support
ms.assetid: 43eb1f14-b129-404a-8806-5bf9b099b67b
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f9a33e8386dcdc2cbf79d057cc454a959b1c06b7
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="supplying-undo-support-to-designers"></a>Poskytuje podporu vrácení zpět, aby Designer
Návrháře, jako je editory, obvykle musí podporovat operace vrácení zpět tak, aby uživatelé mohou provádět jejich poslední změny při úpravě element kódu.  
  
 Většina Designer implementována v sadě Visual Studio je podpora vrácení zpět automaticky poskytované prostředí.  
  
 Návrhář implementace, které je třeba zajistit podporu pro funkci vrácení zpět:  
  
-   Poskytování správy vrácení zpět implementací abstraktní základní třída<xref:System.ComponentModel.Design.UndoEngine>  
  
-   Dodávky trvalosti a CodeDOM podporují implementací <xref:System.ComponentModel.Design.Serialization.IDesignerSerializationService> a <xref:System.ComponentModel.Design.IComponentChangeService> třídy.  
  
 Další informace o zápisu Návrháři pomocí [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], najdete v části [rozšíření podpory návrhu](http://msdn.microsoft.com/Library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2).  
  
 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] Poskytuje infrastrukturu vrácení zpět na výchozí podle:  
  
-   Poskytuje správu implementace prostřednictvím vrátit zpět <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine> a <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine.UndoUnit> třídy.  
  
-   Poskytnutí trvalosti a podpora CodeDOM prostřednictvím výchozí <xref:System.ComponentModel.Design.Serialization.CodeDomComponentSerializationService> a <xref:System.ComponentModel.Design.IComponentChangeService> implementace.  
  
## <a name="obtaining-undo-support-automatically"></a>Automaticky získat podporu pro vrácení zpět  
 Všechny Návrhář vytvořené v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] podporu automatické a úplné vrácení zpět v případě, návrháře:  
  
-   Využívá <xref:System.Windows.Forms.Control> na základě třídy pro jeho uživatelské rozhraní.  
  
-   Aktivuje generování kódu standardní založené na modelu CodeDOM a systém analýzy pro generování kódu a trvalost.  
  
     Další informace o práci s podporou modelu CodeDOM Visual Studio najdete v tématu [dynamické generování zdrojového kódu a kompilace](/dotnet/framework/reflection-and-codedom/dynamic-source-code-generation-and-compilation)  
  
## <a name="when-to-use-explicit-designer-undo-support"></a>Kdy použít podporu explicitní návrháře vrácení zpět  
 Návrháři musíte zadat své vlastní management operace vrácení zpět, pokud používají grafické uživatelské rozhraní, označuje jako adaptér zobrazení, než poskytl <xref:System.Windows.Forms.Control>.  
  
 Příkladem může být vytváření produktu se rozhraní založené na webu grafické návrhu ne [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] na základě grafické rozhraní.  
  
 V takových případech by jeden muset zaregistrovat tento adaptér zobrazení s [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] pomocí <xref:Microsoft.VisualStudio.Shell.Design.ProvideViewAdapterAttribute>a zajistit tak správu explicitní vrácení zpět.  
  
 Návrháři muset zadat CodeDOM a trvalost podporují, pokud se nepoužívají [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] součástí modelu generování kódu <xref:System.CodeDom> obor názvů.  
  
## <a name="undo-support-features-of-the-designer"></a>Vrátit zpět funkce Podpora návrháře  
 Sada SDK prostředí poskytuje výchozí implementaci rozhraní potřebných k poskytování vrátit zpět podpory, které je možné návrháři nepoužíváte <xref:System.Windows.Forms.Control> na základě třídy pro jejich uživatelské rozhraní nebo standardní modelu CodeDOM a trvalost.  
  
 <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine> Třída odvozená z [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] <xref:System.ComponentModel.Design.UndoEngine> pomocí implementace <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoManager> třídy ke správě vrátit zpět operace.  
  
 Visual Studio poskytuje následující funkci tak, aby návrháře vrácení zpět:  
  
-   Propojená operace vrácení zpět funkce napříč více Designer.  
  
-   Podřízené jednotky v rámci návrháře mohou komunikovat s svých nadřazených složek implementací <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoUnit> a <xref:Microsoft.VisualStudio.OLE.Interop.IOleParentUndoUnit> na <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine.UndoUnit>.  
  
 Sada SDK prostředí poskytuje podporu CodeDOM a trvalost zadáním:  
  
-   <xref:System.ComponentModel.Design.Serialization.CodeDomComponentSerializationService>jako implementace<xref:System.ComponentModel.Design.Serialization.IDesignerSerializationService>  
  
 A <xref:System.ComponentModel.Design.IComponentChangeService> poskytované [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]s hostiteli návrhu.  
  
## <a name="using-the-environment-sdk-features-to-supply-undo-support"></a>Pomocí funkce SDK prostředí k poskytování podpory vrácení zpět  
 Pokud chcete získat podporu pro vrácení zpět, musí objekt implementace návrháře:  
  
-   Vytváření instancí a inicializaci instance <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine> třída platný <xref:System.IServiceProvider> implementace.  
  
-   To <xref:System.IServiceProvider> třída musí obsahovat následující služby:  
  
    -   <xref:System.ComponentModel.Design.IDesignerHost>.  
  
    -   <xref:System.ComponentModel.Design.Serialization.IDesignerSerializationService>  
  
         Návrháři pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] serializace CodeDOM rozhodnout použít <xref:System.ComponentModel.Design.Serialization.CodeDomComponentSerializationService> opatřeného [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] jako jeho implementace <xref:System.ComponentModel.Design.Serialization.IDesignerSerializationService>.  
  
         V takovém případě <xref:System.IServiceProvider> třída poskytnuté <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine> konstruktor by měla vrátit tento objekt jako implementaci <xref:System.ComponentModel.Design.Serialization.IDesignerSerializationService> – třída.  
  
    -   <xref:System.ComponentModel.Design.IComponentChangeService>  
  
         Návrháři pomocí výchozího <xref:System.ComponentModel.Design.DesignSurface> poskytované [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] hostiteli návrhu kombinace obsahuje výchozí implementaci třídy <xref:System.ComponentModel.Design.IComponentChangeService> třídy.  
  
 Návrháři implementace <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine> mechanismu vrácení zpět na základě automaticky sleduje změny, pokud:  
  
-   Vlastnost změn prostřednictvím <xref:System.ComponentModel.TypeDescriptor> objektu.  
  
-   <xref:System.ComponentModel.Design.IComponentChangeService>události se generují ručně při vrátit změna se potvrdí.  
  
-   Úprava v Návrháři byl vytvořen v kontextu <xref:System.ComponentModel.Design.DesignerTransaction>.  
  
-   Návrhář rozhodne explicitně vytvořit buď pomocí jednotky zpět standardní zpět jednotku, poskytuje implementaci pro <xref:System.ComponentModel.Design.UndoEngine.UndoUnit> nebo Visual Studio konkrétní implementace <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine.UndoUnit>, která je odvozena z <xref:System.ComponentModel.Design.UndoEngine.UndoUnit> a také poskytuje implementace obou <xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoUnit> a <xref:Microsoft.VisualStudio.OLE.Interop.IOleParentUndoUnit>.  
  
## <a name="see-also"></a>Viz také  
 <xref:System.ComponentModel.Design.UndoEngine>   
 <xref:Microsoft.VisualStudio.Shell.Design.OleUndoEngine>   
 [Rozšíření podpory návrhu](http://msdn.microsoft.com/Library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)