---
title: Sada nástrojů, karta Součásti
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- VS.CHOOSEITEMS.FrameworkComponents
- VS.CHOOSEITEMS.COMComponents
- VS.CHOOSEITEMS.UniversalWindowsComponents
helpviewer_keywords:
- Toolbox, Components tab
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 17f040b9bb64c2192bc6b376f5d0397ee5438071
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2019
ms.locfileid: "66747743"
---
# <a name="toolbox-components-tab"></a>Panel nástrojů, karta součásti

Zobrazí součásti, které můžete přidat do jazyka Visual Basic a C# Návrháře formulářů Windows. Kromě součástí rozhraní .NET, které jsou součástí sady Visual Studio, například <xref:System.Messaging.MessageQueue> a <xref:System.Diagnostics.EventLog> součásti, můžete přidat vaše komponenty třetích stran nebo vlastních na této kartě.

Pokud chcete zobrazit na této kartě, otevřete návrhář formulářů Windows. Vyberte **zobrazení** > **nástrojů**. V **nástrojů**, vyberte **součásti** kartu.

## <a name="components"></a>Komponenty

**BackgroundWorker**

Vytvoří <xref:System.ComponentModel.BackgroundWorker> instance komponenty, který může spouštět operace na oddělené, vyhrazené vlákno. Další informace najdete v tématu [BackgroundWorker – komponenta](/dotnet/framework/winforms/controls/backgroundworker-component).

**DirectoryEntry**

Vytvoří <xref:System.DirectoryServices.DirectoryEntry> instance komponenty, který zapouzdřuje uzel nebo objekt v hierarchii služby Active Directory a umožňuje pracovat s poskytovateli služeb Active Directory.

**DirectorySearcher**

Vytvoří <xref:System.DirectoryServices.DirectorySearcher> instance komponenty, které můžete použít k provádění dotazů vůči Active Directory.

**ErrorProvider**

Vytvoří <xref:System.Windows.Forms.ErrorProvider> instance komponenty, který označuje pro koncového uživatele, že ovládací prvek na formuláři obsahuje chybu s ním spojená. Další informace najdete v tématu [ErrorProvider – komponenta](/dotnet/framework/winforms/controls/errorprovider-component-windows-forms).

**EventLog**

Vytvoří <xref:System.Diagnostics.EventLog> instance komponenty, které můžete použít k interakci se systémem a vlastní protokoly událostí, včetně zápisu události do protokolu a čtení dat protokolu.

**FileSystemWatcher**

Vytvoří <xref:System.IO.FileSystemWatcher> instance komponenty, které můžete použít ke sledování se změní na jakékoli adresář nebo soubor, ke kterému máte přístup.

**HelpProvider**

Vytvoří <xref:System.Windows.Forms.HelpProvider> instance komponenty, která poskytuje místní nápovědu nebo nápovědu online pro ovládací prvky. Další informace najdete v tématu [HelpProvider – komponenta](/dotnet/framework/winforms/controls/helpprovider-component-windows-forms).

**Ovládací prvek ImageList**

Vytvoří <xref:System.Windows.Forms.ImageList> instance komponenty, který poskytuje metody pro správu kolekce <xref:System.Drawing.Image> objekty. Další informace najdete v tématu [komponenty ImageList](/dotnet/framework/winforms/controls/imagelist-component-windows-forms).

**MessageQueue**

Vytvoří <xref:System.Messaging.MessageQueue> instance komponenty, které vám umožní pracovat s fronty zpráv, včetně čtení zpráv ze zápisu zprávy do fronty, zpracování transakcí a provádění úloh správy fronty.

**PerformanceCounter**

Vytvoří <xref:System.Diagnostics.PerformanceCounter> instance komponenty, které vám umožní pracovat s čítače výkonu Windows, včetně vytváření nové kategorie a instance, čtení hodnot z čítačů a provádění výpočtů na data čítače.

**Proces**

Vytvoří <xref:System.Diagnostics.Process> instance komponenty, která můžete použít k zastavení, spuštění a manipulaci s data související s procesy ve vašem systému.

**SerialPort**

Vytvoří <xref:System.IO.Ports.SerialPort> instance komponenty, která umožňuje synchronní a založený na událostech vstupně-výstupních operací, přístup kód pin a přerušení stavů a přístup k vlastnosti sériového portu ovladače.

**ServiceController**

Vytvoří <xref:System.ServiceProcess.ServiceController> instance komponenty, které můžete použít k manipulaci s existujících služeb, včetně spouštění a zastavování služby a posílání příkazů do nich.

**Timer**

Vytvoří <xref:System.Windows.Forms.Timer> instance komponenty, které můžete použít k přidání funkcí založených na čase do vaší aplikace pro systém Windows. Další informace najdete v tématu [komponenty Timer](/dotnet/framework/winforms/controls/timer-component-windows-forms).

> [!NOTE]
> Existuje také systém založen <xref:System.Timers.Timer> , můžete přidat do **nástrojů** to <xref:System.Timers.Timer> je optimalizovaná pro serverové aplikace a Windows Forms <xref:System.Windows.Forms.Timer> je nejvhodnější pro použití v modelu Windows Forms.

## <a name="see-also"></a>Viz také:

- [Ovládací prvky pro použití v modelu Windows Forms](/dotnet/framework/winforms/controls/controls-to-use-on-windows-forms)
- [Zvolit položky panelu nástrojů, součásti WPF](choose-toolbox-items-wpf-components.md)
- [Panel nástrojů](../../ide/reference/toolbox.md)