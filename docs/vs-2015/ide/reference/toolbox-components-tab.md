---
title: Panel nástrojů, karta součásti | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- Toolbox, Components tab
ms.assetid: 332fafab-a763-4244-b388-15d1b5b5cc04
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 0ebbf8a0492537ee40062fb17bb338d46c228a9a
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59652862"
---
# <a name="toolbox-components-tab"></a>Sada nástrojů, karta Součásti
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Zobrazí součásti můžete přidat do [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] a [!INCLUDE[csprcs](../../includes/csprcs-md.md)] návrháře. Kromě [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] součásti, které jsou součástí [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], například <xref:System.Messaging.MessageQueue> a <xref:System.Diagnostics.EventLog> součásti, můžete přidat vaše třetích stran nebo vlastních komponent na této kartě. Další informace najdete v tématu [jak: Manipulace s karty panelu nástrojů](http://msdn.microsoft.com/21285050-cadd-455a-b1f5-a2289a89c4db).  
  
 Zobrazené na této kartě **zobrazení** nabídce vyberte možnost **nástrojů**. V **nástrojů**, vyberte **součásti** kartu.  
  
 **BackgroundWorker**  
 Vytvoří `System.ComponentModel.BackgroundWorker` instance komponenty, který může spouštět operace na oddělené, vyhrazené vlákno.  
  
 **DirectoryEntry**  
 Vytvoří <xref:System.DirectoryServices.DirectoryEntry> instance komponenty, který zapouzdřuje uzel nebo objekt v hierarchii služby Active Directory a umožňuje pracovat s poskytovateli služeb Active Directory.  
  
 **DirectorySearcher**  
 Vytvoří <xref:System.DirectoryServices.DirectorySearcher> instance komponenty, které můžete použít k provádění dotazů vůči Active Directory.  
  
 **ErrorProvider**  
 Vytvoří `System.Windows.Forms.ErrorProvider` instance komponenty, který označuje pro koncového uživatele, že ovládací prvek na formuláři obsahuje chybu s ním spojená.  
  
 **EventLog**  
 Vytvoří <xref:System.Diagnostics.EventLog> instance komponenty, které můžete použít k interakci se systémem a vlastní protokoly událostí, včetně zápisu události do protokolu a čtení dat protokolu. Další informace najdete v tématu [Úvod do protokolu událostí komponenty](http://msdn.microsoft.com/a2ba4f28-4b1a-435e-99ef-51b28e21f805).  
  
 **FileSystemWatcher**  
 Vytvoří <xref:System.IO.FileSystemWatcher> instance komponenty, které můžete použít ke sledování se změní na jakékoli adresář nebo soubor, ke kterému máte přístup. Další informace najdete v tématu [jak: Konfigurace součásti FileSystemWatcher instancí](http://msdn.microsoft.com/2e628234-4951-4135-8a86-28b924070d50).  
  
 **HelpProvider**  
 Vytvoří `System.Windows.Forms.HelpProvider` instance komponenty, která poskytuje místní nápovědu nebo nápovědu online pro ovládací prvky.  
  
 **Ovládací prvek ImageList**  
 Vytvoří `System.Windows.Forms.ImageList` instance komponenty, který poskytuje metody pro správu kolekce `System.Drawing.Image` objekty.  
  
 **MessageQueue**  
 Vytvoří <xref:System.Messaging.MessageQueue> instance komponenty, které vám umožní pracovat s fronty zpráv, včetně čtení zpráv ze zápisu zprávy do fronty, zpracování transakcí a provádění úloh správy fronty. Další informace najdete v tématu [pomocí součásti zasílání zpráv](http://msdn.microsoft.com/922dbac7-26f0-4e39-b666-ccfc184793d7).  
  
 **PerformanceCounter**  
 Vytvoří <xref:System.Diagnostics.PerformanceCounter> instance komponenty, které vám umožní pracovat s čítače výkonu Windows, včetně vytváření nové kategorie a instance, čtení hodnot z čítačů a provádění výpočtů na data čítače. Další informace najdete v tématu [monitorování prahové hodnoty výkonu](http://msdn.microsoft.com/b8b44a55-31d0-4b45-9517-8c1b1e4fdc91).  
  
 **Proces**  
 Vytvoří <xref:System.Diagnostics.Process> instance komponenty, která můžete použít k zastavení, spuštění a manipulaci s data související s procesy ve vašem systému. Další informace najdete v tématu [monitorování a Správa procesů Windows](http://msdn.microsoft.com/a86bd4c1-b92c-49a0-8f32-61d67837b45e).  
  
 **SerialPort**  
 Vytvoří `System.IO.Ports.SerialPort` instance komponenty, která umožňuje synchronní a založený na událostech vstupně-výstupních operací, přístup kód pin a přerušení stavů a přístup k vlastnosti sériového portu ovladače.  
  
 **ServiceController**  
 Vytvoří <xref:System.ServiceProcess.ServiceController> instance komponenty, které můžete použít k manipulaci s existujících služeb, včetně spouštění a zastavování služby a posílání příkazů do nich. Další informace najdete v tématu [sledování služby Windows](http://msdn.microsoft.com/4542ee3f-e052-4cb9-8726-58e9420de222).  
  
 **Timer**  
 Vytvoří <xref:System.Windows.Forms.Timer> instance komponenty, které můžete použít k přidání funkcí založených na čase do vaší aplikace pro systém Windows. Další informace najdete v tématu [komponenty Timer](http://msdn.microsoft.com/library/6700e534-6382-43d5-98ed-14205435fff7).  
  
> [!NOTE]
>  Existuje také systém založen <xref:System.Timers.Timer> , můžete přidat do **nástrojů** to <xref:System.Timers.Timer> je optimalizovaná pro serverové aplikace a Windows Forms <xref:System.Windows.Forms.Timer> je nejvhodnější pro použití v modelu Windows Forms.  
  
## <a name="see-also"></a>Viz také  
 [Programování pomocí komponent](http://msdn.microsoft.com/library/d4d4fcb4-e0b8-46b3-b679-7ee0026eb9e3)   
 [Návody pro programování komponent](http://msdn.microsoft.com/library/373cacf7-479e-4b05-991c-5cb18824e913)   
 [Panel nástrojů](../../ide/reference/toolbox.md)   
 [Zvolte dialogové okno položky panelu nástrojů (Visual Studio)](http://msdn.microsoft.com/bd07835f-18a8-433e-bccc-7141f65263bb)
