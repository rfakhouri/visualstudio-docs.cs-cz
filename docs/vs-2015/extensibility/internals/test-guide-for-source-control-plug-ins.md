---
title: Testovací Příručka pro ovládací prvek moduly plug-in zdrojového kódu | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- plug-ins, source control
- source control [Visual Studio SDK], testing plug-ins
- tests, source control plug-ins
- testing, source control plug-ins
- source control plug-ins, test guide
ms.assetid: 13b74765-0b7c-418e-8cd9-5f2e8db51ae5
caps.latest.revision: 27
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 6790e61eddc81045bb168028ee7aeef7a0492e3c
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/11/2019
ms.locfileid: "67825751"
---
# <a name="test-guide-for-source-control-plug-ins"></a>Testovací příručka pro moduly plug-in správy zdrojového kódu
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Tato část obsahuje pokyny pro testování vašich plug-in správy zdrojových kódů s [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Je k dispozici rozsáhlý přehled nejběžnějších oblastí testování, jakož i některé komplikovanější oblastí, které může být problematické. Tento přehled není určena k tudíž nepředstavuje kompletní seznam testovacích případů.  
  
> [!NOTE]
> Několik oprav chyb a vylepšení na nejnovější verzi [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] integrovaného vývojového prostředí může odhalit problémy s existující ovládací prvek moduly plug-in zdrojového kódu, které dříve nebyly nalezeny při používání předchozích verzích [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]. Důrazně doporučujeme, jakým testujete vaše stávající plug-in správy zdrojových kódů pro oblasti, které jsou uvedené v této části i v případě, že byly provedeny žádné změny v modulu plug-in od předchozí verze [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)].  
  
## <a name="common-preparation"></a>Běžné přípravy  
 Počítač s [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] a nainstalovaný, je potřeba cílového plug-in správy zdrojových kódů. Do druhého počítače podobně nakonfigurovaného lze použít pro některý ze otevřít ze správy zdrojových kódů testy.  
  
## <a name="definition-of-terms"></a>Definice pojmů  
 Pro účely tohoto průvodce testu použijte následující definice období:  
  
 Klientský projekt  
 Žádný typ k dispozici v projektu [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] integrace správy zdrojového kódu, která podporuje (třeba [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)], [!INCLUDE[csprcs](../../includes/csprcs-md.md)], nebo [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)]).  
  
 Webový projekt  
 Existují čtyři typy webových projektů: Systém souborů, místní služby IIS, vzdálených lokalit a FTP.  
  
- Projekty systému souborů se vytvoří v místní cestě, ale nevyžadují Internet informační služby (IIS) k instalaci tak, jak interně přistupuje pomocí cesty UNC a můžete umístit pod správou zdrojových kódů z zevnitř rozhraní IDE, podobně jako klientské projekty.  
  
- Místní služby IIS projekty pracovat s IIS, která je nainstalovaná na stejném počítači a ke kterým se přistupuje pomocí adresy URL odkazující na místním počítači.  
  
- Projekty vzdálené lokality se také vytvoří v rámci služby IIS, ale jsou umístěny pod správou zdrojového kódu na počítači serveru služby IIS a ne z uvnitř [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] integrovaného vývojového prostředí.  
  
- FTP projekty jsou přístupné prostřednictvím vzdáleného serveru FTP, ale nemůže být umístěn pod správou zdrojových kódů.  
  
  Zařazení  
  Jiný termín pro řešení nebo projekt pod správou zdrojových kódů.  
  
  Verze Store  
  Databázi správy zdrojových kódů, které je přistupováno prostřednictvím rozhraní API modulu Plug-in zdroje ovládacího prvku.  
  
## <a name="test-areas-covered-in-this-section"></a>Oblasti testů, které jsou popsané v této části  
  
- [Testovací oblast 1: Přidání nebo otevření ze správy zdrojového kódu](../../extensibility/internals/test-area-1-add-to-open-from-source-control.md)  
  
  - Případu 1a: Přidat řešení do správy zdrojového kódu  

  - Případu 1b: Otevřít řešení ze správy zdrojového kódu  

  - Případ 1c: Přidat řešení ze správy zdrojového kódu  

- [Testovací oblast 2: Získání ze správy zdrojového kódu](../../extensibility/internals/test-area-2-get-from-source-control.md)  
  
- [Testovací oblast 3: Rezervace a zrušení rezervace](../../extensibility/internals/test-area-3-check-out-undo-checkout.md)  
  
  - Případ 3: Podívejte se na / Zrušit rezervaci  

  - Případu 3a: Rezervovat  

  - Případu 3b: Odpojené rezervace  

  - Případ 3c: Query Edit/Query Save (QEQS)  

  - Malá a velká 3d: Bezobslužné ověření  

  - Případu 3e: Vrátit zpět rezervaci  
  
- [Testovací oblast 4: Vrácení se změnami](../../extensibility/internals/test-area-4-check-in.md)  
  
  - Případu 4a: Změněné položky  

  - Případu 4b: Přidávání souborů  

  - Případ 4c: Přidávání projektů  
  
- [Testovací oblast 5: Změna správy zdrojového kódu](../../extensibility/internals/test-area-5-change-source-control.md)  
  
  - Případu 5a: Vytvoření vazby  

  - Případu 5b: Zrušení vazby  

  - Případ 5c: obnovení vazby  

- [Testovací oblast 6: Odstranění](../../extensibility/internals/test-area-6-delete.md)  

- [Testovací oblast 7: Sdílení](../../extensibility/internals/test-area-7-share.md)  

- [Testovací oblast 8: Přepínání modulů plug-in](../../extensibility/internals/test-area-8-plug-in-switching.md)  

  - Případu 8a: Automaticky změnit  

  - Případu 8b: Řešení na základě změn  

## <a name="see-also"></a>Viz také  
 [Moduly plug-in správy zdrojového kódu](../../extensibility/source-control-plug-ins.md)
