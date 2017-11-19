---
title: "Přehled řešení | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: solutions, about solutions
ms.assetid: 3b21e3a1-170a-4485-941e-6b04b7b27886
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a6a1afea2357fb0c0ef1bcf8152f8a3785a55786
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="solutions-overview"></a>Přehled řešení
Řešení je skupina jednoho nebo více projektů, které vzájemně spolupracují a vytvoření aplikace. Informace o projektu a stav týkající se řešení jsou uloženy ve dvou souborech jiné řešení. Soubor řešení (.sln) je založený na textu a můžete umístit ve správě zdrojového kódu a sdílet mezi uživateli. Je binární soubor řešení uživatele možnost (.suo). V důsledku toho .suo soubor nemůže být umístěn v zdrojového kódu a obsahuje informace o uživateli.  
  
 Všechny VSPackage může zapisovat do libovolného soubor řešení. Vzhledem k povaze soubory jsou dvě různé rozhraní implementované zapisovat do nich. <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps> Rozhraní zapisuje informace textový soubor .sln a <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts> rozhraní zapisuje do souboru .suo binární datové proudy.  
  
> [!NOTE]
>  Není nutné explicitně zápis záznamu pro sebe sama do souboru řešení; projektu prostředí, zpracovává pro projekt. Proto pokud chcete přidat další obsah určený speciálně pro soubor řešení, není potřeba zaregistrovat vaše VSPackage tímto způsobem.  
  
 Každý VSPackage podpora trvalost řešení používá tři rozhraní, <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence> rozhraní, které je implementované v prostředí a volány VSPackage, a `IVsPersistSolutionProps` a `IVsPersistSolutionOpts`, které jsou obě implementována VSPackage. `IVsPersistSolutionOpts` Rozhraní pouze musí být implementována, pokud má být zapsána pomocí VSPackage do souboru .suo soukromé informace.  
  
 Po otevření řešení následující proces probíhá.  
  
1.  Prostředí přečte řešení.  
  
2.  Pokud najde prostředí `CLSID`, načte odpovídající VSPackage.  
  
3.  Pokud je VSPackage načteny, volání prostředí `QueryInterface` pro <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage> rozhraní pro rozhraní, které VSPackage vyžaduje.  
  
    1.  Při čtení ze souboru .sln, prostředí volá `QueryInterface` pro `IVsPersistSolutionProps`.  
  
    2.  Při čtení ze souboru .suo, prostředí volá `QueryInterface` pro `IVsPersistSolutionOpts`.  
  
 Konkrétní informace týkající se používání těchto souborů naleznete v [řešení (. SLN –) soubor](../../extensibility/internals/solution-dot-sln-file.md) a [uživatelské možnosti řešení (. Suo) soubor](../../extensibility/internals/solution-user-options-dot-suo-file.md).  
  
> [!NOTE]
>  Pokud chcete vytvořit novou konfiguraci řešení skládající se z konfigurace dva projekty s výjimkou třetí z buildu, budete muset použít uživatelského rozhraní stránky vlastností nebo automatizace. Nelze změnit správce konfigurace sestavení řešení a jejich vlastnosti přímo, ale můžete upravit ke Správci sestavení řešení pomocí `SolutionBuild` třídy z prostředí DTE v modelu automatizace. Další informace o konfiguraci řešení najdete v tématu [konfigurace řešení](../../extensibility/internals/solution-configuration.md).  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence>