---
title: Dialogové okno Nastavit odkaz na službu
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- msvse_wcf.dlg.ConfigureServiceReference
helpviewer_keywords:
- WCF services, Configure Service Reference dialog box
- service references [Visual Studio], configuring behavior
- Configure Service Reference dialog box
ms.assetid: 25e4c36b-2db6-4e71-9010-b7068255d09d
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 93d39aedc04cbdaebc35c892a8393ca394f44898
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/20/2018
ms.locfileid: "36281063"
---
# <a name="configure-service-reference-dialog-box"></a>Dialogové okno Nastavit odkaz na službu

**Nastavit odkaz na službu** dialogové okno umožňuje konfigurovat chování služby Windows Communication Foundation (WCF).

> [!NOTE]
> Dialogová okna a příkazy nabídek, které vidíte, se mohou lišit od těch popsaných v nápovědě v závislosti na aktivních nastaveních nebo edici. Chcete-li změnit nastavení, zvolte **nastavení importu a exportu** na **nástroje** nabídky. Další informace najdete v tématu [přizpůsobení prostředí Visual Studio IDE](../ide/personalizing-the-visual-studio-ide.md).

Pro přístup k **nastavit odkaz na službu** dialogové okno, klikněte pravým tlačítkem na může služba odkaz v **Průzkumníku řešení** a zvolte **nastavit odkaz na službu**. Můžete také přístup k dialogu kliknutím **Upřesnit** tlačítka na **přidat služby odkaz dialogové okno**.

## <a name="task-list"></a>Seznam úkolů

- Chcete-li změnit adresu, která je hostitelem služby WCF, zadejte nové adresy v **adresu** pole.

- Pokud chcete změnit úroveň přístupu pro třídy v klientovi WCF, vyberte úroveň přístupu klíčové slovo v **přístup úroveň pro vygenerované třídy** seznamu.

- Asynchronní volání metody služby WCF, vyberte **Generovat asynchronní operace** zaškrtávací políčko.

- Chcete-li vygenerovat typy kontraktů zpráv v klienta WCF, vyberte **vždy generovat kontrakty zpráv** zaškrtávací políčko.

- Typy kolekcí seznamu nebo slovník pro klienta WCF, vyberte typy z **– typ kolekce** a **– typ kolekce slovníku** uvádí.

- Chcete-li vypnout sdílení typu, zrušte **znovu použít typy v odkazovaných sestaveních** zaškrtávací políčko. Chcete-li povolit sdílení typu pro podmnožinu odkazovaná sestavení, vyberte **znovu použít typy v odkazovaných sestaveních** zaškrtněte políčko **znovu použít typy v odkazovaných sestaveních**a vyberte požadovanou odkazy na v **odkazovaný seznam sestavení**.

## <a name="uielement-list"></a>Seznam prvků uživatelského rozhraní

 **Adresa**

 Aktualizuje webovou adresu, kde odkazu na službu hledá službu. Například během vývoje, služba může být hostovaný na serveru vývoj a později přesunout na provozním serveru vyžadující změnu adresy.

> [!NOTE]
> Address element není k dispozici při **nastavit odkaz na službu** dialogové okno se zobrazí z **přidat Service Reference Dialog Box**.

 **Úroveň přístupu pro vygenerované třídy**

 Určuje úroveň přístupu třídy klienta WCF v kódu.

> [!NOTE]
> Pro projekty webových stránek, je tato možnost vždycky nastavený na `Public` a nelze je změnit. Další informace najdete v tématu [řešení potíží s odkazy na službu](../data-tools/troubleshooting-service-references.md).

 **Generovat asynchronní operace**

 Určuje, zda je synchronně volat metody služby WCF (výchozí) nebo asynchronně.

 **Generování operací založený na úlohách**

 Při psaní kódu pro asynchronní, tato možnost umožňuje využívat nástroje Task Parallel Library (TPL) byla zavedena s .NET 4. V tématu [úkolů Parallel Library (TPL)](/dotnet/standard/parallel-programming/task-parallel-library-tpl).

 **Vždy generovat kontrakty zpráv**

 Určuje, zda jsou pro klienta WCF generovány typy kontraktů zpráv. Další informace o kontrakty zpráv najdete v tématu [použití kontraktů zpráv](/dotnet/framework/wcf/feature-details/using-message-contracts).

 **Typ kolekce**

 Určuje typ kolekce seznamu pro klienta WCF. Je výchozím typem <xref:System.Array>.

 **Slovník – typ kolekce**

 Určuje typ kolekce slovníku pro klienta WCF. Je výchozím typem <xref:System.Collections.Generic.Dictionary%602>.

 **Znovu použít typy v odkazovaných sestaveních**

 Určuje, zda klienta WCF se pokusí znovu použít, co již existuje v odkazovaných sestaveních namísto generování nových typů, když je služba přidán nebo aktualizován. Ve výchozím nastavení je toto políčko zaškrtnuto.

 **Znovu použít typy v odkazovaných sestaveních pro všechny**

 Pokud vybraná, všechny typy v **odkazovaný seznam sestavení** jsou opakovaně Pokud je to možné. Ve výchozím nastavení je tato možnost vybrána.

 **Znovu použít typy v odkazovaných sestaveních**

 Při výběru pouze vybrané typy v **odkazovaný seznam sestavení** jsou opakovaně.

 **Seznam odkazovaná sestavení**

 Obsahuje seznam odkazovaná sestavení projektu nebo webu. Když vyberete **znovu použít typy v odkazovaných sestaveních**, můžete zaškrtněte nebo zrušte jednotlivá sestavení.

 **Přidat odkaz na Web**

 Zobrazí **přidat odkaz na Web** dialogové okno.

> [!NOTE]
> Tato možnost slouží pouze pro projekty, které cílí na verzi 2.0 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].

> [!NOTE]
> **Přidat odkaz na Web** tlačítko je k dispozici pouze při **nastavit odkaz na službu** dialogové okno se zobrazí z **přidat Service Reference Dialog Box**.

## <a name="see-also"></a>Viz také:

- [Postupy: Přidání odkazu na webovou službu](how-to-add-update-or-remove-a-wcf-data-service-reference.md)
- [Služby Windows Communication Foundation a služby WCF Data Services v sadě Visual Studio](../data-tools/configure-service-reference-dialog-box.md)