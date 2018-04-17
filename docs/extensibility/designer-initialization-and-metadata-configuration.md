---
title: Návrhář inicializace a konfigurace Metadata | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- designers [Visual Studio SDK], initializing
- designers [Visual Studio SDK], configuring metadata
ms.assetid: f7fe9a7e-f669-4642-ad5d-186b2e6e6ec9
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a6334f65b942b2eab3543d866ae1b98a186569ea
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="designer-initialization-and-metadata-configuration"></a>Návrhář inicializace a konfigurace metadat
Manipulace s metadat a filtrování atributů spojených s designer nebo součástí návrháře poskytuje mechanismus pro aplikace, můžete definovat, které nástroje se používají konkrétní designeru pro zpracování různých <xref:System.Type> objekty (například datové struktury třídy nebo grafické entity), pokud není k dispozici návrháře a konfiguraci prostředí Visual Studio IDE pro podporu návrháře (pro instanci, která **sada nástrojů** kategorie nebo karta je k dispozici).  
  
 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] Poskytuje několik mechanismů usnadňuje řízení návrháře nebo součástí návrháře inicializace a manipulace s jeho metadat pomocí VSPackage.  
  
## <a name="initializing-metadata-and-configuration-information"></a>Inicializace metadat a informace o konfiguraci  
 Protože jsou načteny na vyžádání, VSPackages nemusí byly načteny [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] prostředí před vytvořením instance návrháře. Proto VSPackages nemůže použít standardní mechanismus konfigurace designer nebo návrháře součást pro vytváření, což je pro zpracování <xref:System.ComponentModel.Design.IDesignerEventService.DesignerCreated> událostí. Místo toho VSPackage implementuje instanci <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension> rozhraní a registruje zajistit úprav, označuje jako rozšíření prostor návrhu.  
  
### <a name="customizing-initialization"></a>Přizpůsobení inicializace  
 Přizpůsobení návrháře, komponenty nebo plochu návrháře zahrnuje:  
  
1.  Úprava návrháře metadata a efektivně změna jak určitou <xref:System.Type> získat přístup nebo převést.  
  
     To se obvykle provádí pomocí <xref:System.Drawing.Design.UITypeEditor> nebo <xref:System.ComponentModel.TypeConverter> mechanismy.  
  
     Například, když <xref:System.Windows.Forms>-jsou inicializovány na základě Designer, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] upraví prostředí <xref:System.Drawing.Design.UITypeEditor> pro <xref:System.Web.UI.WebControls.Image> objekty použít s návrhářem získat bitmap místo systému souborů pomocí Správce prostředků.  
  
2.  Integrace s prostředím, například přihlášení k odběru událostí nebo získat informace o konfiguraci projektu. Můžete získat informace o konfiguraci projektu a přihlásit k odběru událostí prostřednictvím provedeného <xref:System.ComponentModel.Design.ITypeResolutionService> rozhraní.  
  
3.  Změna uživatelského prostředí aktivací odpovídající **sada nástrojů** kategorie nebo omezením návrháři použitelnosti použitím instanci <xref:System.ComponentModel.ToolboxItemFilterAttribute> třídy návrháře.  
  
### <a name="designer-initialization-by-a-vspackage"></a>Návrhář inicializace podle VSPackage  
 VSPackage by měla řídit návrháře inicializace podle:  
  
1.  Vytvoření implementace objektu <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension> třídy.  
  
    > [!NOTE]
    >  <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension> Třída by měla být nikdy implementována pro stejný objekt, jako <xref:Microsoft.VisualStudio.Shell.Package> třídy.  
  
2.  Registrovat třídu implementace <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension> jako zajištění podpory pro rozšíření návrháře VSPackage použitím instancí <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtensionAttribute>, <xref:Microsoft.VisualStudio.Shell.ProvideObjectAttribute> a <xref:Microsoft.VisualStudio.Shell.ProvideServiceAttribute> k třídě poskytuje implementaci VSPackage <xref:Microsoft.VisualStudio.Shell.Package> .  
  
 Vždy, když všechny designer nebo součástí návrháře je vytvořen, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] prostředí:  
  
1.  Přistupuje k poskytovateli prostor rozšíření každý registrovaný návrhu.  
  
2.  Vytvoří a inicializuje instanci poskytovatele každého návrhu prostor rozšíření <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension> objektu  
  
3.  Volá každý poskytovatel prostor rozšíření návrhu <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension.OnDesignerCreated%2A> metoda nebo <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension.OnComponentCreated%2A> – metoda (podle potřeby).  
  
 Při implementaci <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension> objektu jako člen skupiny VSPackage, je důležité pochopit, že:  
  
1.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Prostředí nenabízí žádné kontrolu nad jaká metadata nebo dalších nastavení konfigurace a konkrétní `DesignSurfaceExtension` upraví poskytovatele. Je možné pro dva nebo více `DesignSurfaceExtension` zprostředkovatelé úprava funkci stejné návrháře konfliktní způsoby s finální úpravy se spolehlivý. Je neurčitém poslední úpravy, které platí.  
  
2.  Je možné explicitně omezit implementace <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension> objekt, který chcete konkrétní návrháře, použitím instancí <xref:System.ComponentModel.ToolboxItemFilterAttribute> pro tuto implementaci. Další informace o **sada nástrojů** položky filtrování najdete v tématu <xref:System.ComponentModel.ToolboxItemFilterAttribute> a <xref:System.ComponentModel.ToolboxItemFilterType>.  
  
## <a name="additional-metadata-provisioning"></a>Zřizování dalších metadat  
 VSPackage můžete změnit konfiguraci designer nebo součástí návrháře jinak než v době návrhu.  
  
 <xref:Microsoft.VisualStudio.Shell.Design.ProvideDesignerMetadataAttribute> Třídy lze programově, nebo použít na VSPackage poskytování návrháře.  
  
 Instance <xref:Microsoft.VisualStudio.Shell.Design.ProvideDesignerMetadataAttribute> třída slouží k úpravě metadata komponenty vytvořené na návrhovou plochu. Například jeden může nahradit výchozí vlastnost prohlížeč používá <xref:System.Windows.Forms.CommonDialog> objekty s prohlížečem, a vlastní vlastnosti.  
  
 Úpravy poskytované instanci <xref:Microsoft.VisualStudio.Shell.Design.ProvideDesignerMetadataAttribute> použít k implementaci VSPackage <xref:Microsoft.VisualStudio.Shell.Package> může mít jeden ze dvou obory:  
  
-   Globální – pro všechny nové instance dané komponenty  
  
-   Místní –, která se týkají pouze instanci komponenty na návrhovou plochu poskytované aktuální VSPackage vytvořit.  
  
 `IsGlobal` Vlastnost <xref:Microsoft.VisualStudio.Shell.Design.ProvideDesignerMetadataAttribute> instance použít k implementaci VSPackage <xref:Microsoft.VisualStudio.Shell.Package> určuje tento obor.  
  
 Použití atributu implementace <xref:Microsoft.VisualStudio.Shell.Package> s <xref:Microsoft.VisualStudio.Shell.Design.ProvideDesignerMetadataAttribute.IsGlobal%2A> vlastnost <xref:Microsoft.VisualStudio.Shell.Design.ProvideDesignerMetadataAttribute> nastavení objektu `true`, jako níže změní prohlížeče pro celý [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] prostředí:  
  
 `[ProvideDesignerMetadata(typeof(Color), typeof(CustomBrowser),`   `IsGlobal=true`  `)]`  
  
 `internal class MyPackage : Package {}`  
  
 Pokud byl nastaven příznak globální do `false`, pak je lokální vzhledem k aktuální designer nepodporuje aktuální VSPackage změnu metadat:  
  
 `[ProvideDesignerMetadata(typeof(Color), typeof(CustomBrowser),`   `IsGlobal=false`  `)]`  
  
 `internal class MyPackage : Package {}`  
  
> [!NOTE]
>  V současné době návrhovou plochu, která podporuje pouze vytváření komponenty, a proto může mít pouze komponenty místních metadat. V předchozím příkladu jsme se pokouší změnit vlastnost, například `Color` vlastnost objektu. Pokud `false` byla předána pro globální příznak `CustomBrowser` by nikdy vypadat, protože návrháře vytvoří ve skutečnosti instance `Color`. Nastavení příznaku globální `false` je užitečné pro součásti, jako jsou ovládací prvky, časovače a dialogová okna.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtension>   
 <xref:Microsoft.VisualStudio.Shell.Design.DesignSurfaceExtensionAttribute>   
 <xref:System.ComponentModel.ToolboxItemFilterType>   
 [Rozšíření podpory návrhu](http://msdn.microsoft.com/Library/d6ac8a6a-42fd-4bc8-bf33-b212811297e2)