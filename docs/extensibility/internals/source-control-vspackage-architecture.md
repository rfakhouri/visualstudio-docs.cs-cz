---
title: Zdrojová architektura VSPackage řízení | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control packages, architecture
ms.assetid: 453125fc-23dc-49b1-8476-94581f05e6c7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: a423b270eb8a26e9573f957da48915db37bf6851
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="source-control-vspackage-architecture"></a>Architektura VSPackage zdroj ovládacího prvku
Balíček správy zdrojového kódu se VSPackage, který používá služby, které [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] poskytuje IDE. Balíček správy zdrojového kódu, poskytuje jeho funkce jako zdroj řízení služby. Kromě toho je balíček správy zdrojového kódu rozmanitější alternativní než zdrojového kódu pro integraci správy zdrojového kódu do modulu plug-in [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 Správa zdrojového kódu modul plug-in, která implementuje rozhraní API ovládacího prvku Plug-in Zdroj dodržuje kontraktu strict. Například modul plug-in nelze nahradit výchozí [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] uživatelské rozhraní (UI). Kromě toho rozhraní API ovládacího prvku Plug-in zdroj není povolen modul plug-in, implementovat vlastní ovládací prvek modelu zdroje. Balíček správy zdrojového kódu, ale překonává obě tato omezení. Balíček správy zdrojového kódu má plnou kontrolu nad možností řízení zdroje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] uživatele. Kromě toho balíček správy zdrojového kódu můžete použít vlastní ovládací prvek modelu zdroje a logiku, a může definovat všechny související ovládací prvek uživatelského rozhraní zdroje.  
  
## <a name="source-control-package-components"></a>Balíček součástí zdrojového kódu  
 Jak je znázorněno v diagram architektury [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] součást s názvem Stub řízení zdroj je VSPackage spolupracující se balíček správy zdrojového kódu se [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 Zdroj ovládacího prvku se zakázaným inzerováním zpracovává následující úlohy.  
  
-   Poskytuje společné rozhraní, které je potřeba k registraci balíček správy zdrojového kódu.  
  
-   Načte balíček správy zdrojového kódu.  
  
-   Balíček správy zdrojového kódu se nastaví jako aktivní nebo neaktivní.  
  
 Zdroj ovládacího prvku se zakázaným inzerováním vypadá pro službu active pro balíček správy zdrojového kódu a směruje všechny příchozí volání služby z rozhraní IDE pro tento balíček.  
  
 Zdrojový balíček ovládací adaptéru je speciální zdrojového balíčku, který [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] poskytuje. Tento balíček je ústřední součást pro podporu zdroj ovládacího prvku moduly plug-in založené na rozhraní API ovládacího prvku Plug-in zdroje. Modul plug-in správy zdroje je modul plug-in aktivní, zástupná procedura zdroj ovládacího prvku odesílá do zdrojový balíček ovládací adaptéru jeho události. Naopak zdrojový balíček ovládací adaptéru komunikuje se správa zdrojového kódu modulu plug-in pomocí rozhraní API ovládacího prvku Plug-in zdroje a také poskytuje výchozí uživatelského rozhraní, které jsou společné pro všechny zdroje řízení moduly plug-in.  
  
 Balíček active po balíček správy zdrojového kódu na druhé straně Stub řízení zdroj přímo komunikuje se balíček pomocí [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] rozhraní správy zdroje balíčku. Balíček správy zdrojového kódu je zodpovědná za hostování vlastní zdroj ovládacího prvku uživatelského rozhraní.  
  
 ![Architektura ovládacího prvku obrázek zdroj](../../extensibility/internals/media/vsipsccarch.gif "VSIPSCCArch")  
  
 Pro balíček správy zdrojového kódu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] neposkytuje zdrojový kód ovládací prvek nebo rozhraní API pro integraci produktů. Tento rozdíl oproti přístup uvedených v [vytvoření modulu Plugin zdroj ovládacího prvku](../../extensibility/internals/creating-a-source-control-plug-in.md) kde má modul plug-in správy zdroje k implementaci pevné sadu funkcí a zpětná volání.  
  
 Podobně jako všechny VSPackage balíček správy zdrojového kódu je objekt modelu COM, která se dají vytvořit pomocí `CoCreateInstance`. VSPackage umožňuje přístup ke [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE implementací <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>. Při vytvoření instance VSPackage obdrží ukazatel lokality a <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> rozhraní, které poskytuje přístup VSPackage dostupných služeb a rozhraní IDE.  
  
 Zápis na základě VSPackage zdrojového balíčku vyžaduje pokročilejší znalosti programování než zápis zdroj ovládacího prvku Plug-in založené na rozhraní API modulu plug-in.  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>   
 [Začínáme](../../extensibility/internals/getting-started-with-source-control-vspackages.md)