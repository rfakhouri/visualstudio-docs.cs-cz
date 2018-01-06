---
title: "Průvodce pro zdroj ovládacího prvku zásuvné moduly testovací | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- plug-ins, source control
- source control [Visual Studio SDK], testing plug-ins
- tests, source control plug-ins
- testing, source control plug-ins
- source control plug-ins, test guide
ms.assetid: 13b74765-0b7c-418e-8cd9-5f2e8db51ae5
caps.latest.revision: "26"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0fdab6cb0b259fe169a9ebd43c92158a5ce20d4b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="test-guide-for-source-control-plug-ins"></a>Příručka pro testovací modulů plug-in programu zdroj ovládacího prvku
Tato část obsahuje pokyny pro testování vaší zdrojového kódu pomocí modulu plug-in [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Přehled rozsáhlé nejběžnější testování oblastech, jakož i některé z komplikovanější oblastí, které mohou způsobovat je k dispozici. Tento přehled není určená jako vyčerpávající seznam testovací případy.  
  
> [!NOTE]
>  Některé opravy chyb a vylepšení nejnovější [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE může odkrýt problémy s existující zdroj ovládacího prvku zásuvné moduly, které nebyly dříve došlo při používání předchozích verzích [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]. Důrazně doporučujeme, abyste otestovali vaší existující modulu plug-in pro oblasti uvedené v této části zdrojového kódu i v případě, že byly provedeny žádné změny v modulu plug-in od předchozí verze [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
## <a name="common-preparation"></a>Běžné přípravy  
 Počítač s [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] a zdroje pro cílový ovládací prvek modulu plug-in nainstalovaná, je potřeba. Druhý počítač nakonfigurovaný Podobně lze použít pro některé otevření ze zdrojového kódu testy.  
  
## <a name="definition-of-terms"></a>Definice pojmů  
 Pro účely tohoto průvodce testovací použijte následující definice období:  
  
 Klientského projektu  
 Žádný typ, které jsou k dispozici v projektu [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] podporující integrace ovládacích prvků zdrojového (například [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)], [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)], nebo [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)]).  
  
 Webového projektu  
 Existují čtyři typy webové projekty: systém souborů, místní služba IIS, vzdálenými lokalitami a FTP.  
  
-   Projektů v systému souborů, které jsou vytvořené v místní cestě, ale nevyžadují Internetové informační služby (IIS) nainstalovaná, jak interně přistupuje pomocí cesty UNC a může být umístěn v zdrojového kódu z uvnitř integrovaného vývojového prostředí, podobně jako klient projekty.  
  
-   Místní projekty služby IIS pracovat se službou IIS, který je nainstalovaný na stejném počítači a ke kterým se přistupuje pomocí adresy URL odkazující na místním počítači.  
  
-   Vzdálené lokality projekty jsou také vytvářeny pod služby IIS, ale jsou umístěny ve správě zdrojového kódu na počítači serveru služby IIS a nikoli z uvnitř [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
-   FTP projekty jsou přístupné prostřednictvím vzdáleného serveru FTP, ale nemůže být umístěn v části Správa zdrojového kódu.  
  
 Zařazení  
 Jiný termín pro řešení nebo projektu ve správě zdrojového kódu.  
  
 Úložiště verzí  
 Zdroj ovládacího prvku databáze, která přistupuje prostřednictvím rozhraní API ovládacího prvku Plug-in zdroje.  
  
## <a name="test-areas-covered-in-this-section"></a>Testovací oblasti uvedenými v této části  
  
-   [Oblasti test 1: Přidání do nebo otevřete od správy zdrojového kódu](../../extensibility/internals/test-area-1-add-to-open-from-source-control.md)  
  
    -   Případ 1a: přidání řešení do správy zdrojového kódu  
  
    -   Případ 1b: otevřete řešení od správy zdrojového kódu  
  
    -   Případ 1c: Přidat řešení od správy zdrojového kódu  
  
-   [Testovací oblast 2: Načtení ze správy zdrojového kódu](../../extensibility/internals/test-area-2-get-from-source-control.md)  
  
-   [Test oblasti 3: Rezervovat / vrátit zpět rezervaci](../../extensibility/internals/test-area-3-check-out-undo-checkout.md)  
  
    -   Případ 3: Rezervovat / vrátit zpět rezervaci  
  
    -   Případ 3a: Podívejte se na  
  
    -   Případ 3b: odpojení rezervovat  
  
    -   Případ 3c: Upravit dotaz nebo dotaz uložit (QEQS)  
  
    -   Případ 3d: Tichou Checkout  
  
    -   Případ 3e: vrátit zpět rezervaci  
  
-   [Testovací oblast 4: Vrácení se změnami](../../extensibility/internals/test-area-4-check-in.md)  
  
    -   Případ 4a: Upravit položky  
  
    -   Případ 4b: přidávání souborů  
  
    -   Případ 4c: Přidání projektů  
  
-   [Testovací oblast 5: Změna správy zdrojového kódu](../../extensibility/internals/test-area-5-change-source-control.md)  
  
    -   Případ 5a: vytvoření vazby  
  
    -   Případ 5b: odpojení  
  
    -   Případ 5c: Rebind  
  
-   [Testovací oblast 6: Odstranění](../../extensibility/internals/test-area-6-delete.md)  
  
-   [Testovací oblast 7: Sdílení](../../extensibility/internals/test-area-7-share.md)  
  
-   [Testovací oblast 8: Přepínání modulu plug-in](../../extensibility/internals/test-area-8-plug-in-switching.md)  
  
    -   Případ 8a: Automatická změna  
  
    -   Případ 8b: na základě řešení změn  
  
## <a name="see-also"></a>Viz také  
 [Moduly plug-in správy zdrojového kódu](../../extensibility/source-control-plug-ins.md)