---
title: Programu zlepšování zkušeností zákazníků
description: Zjistěte, jak spravovat nastavení ochrany osobních údajů v sadě Visual Studio.
ms.date: 05/21/2018
ms.prod: visual-studio-dev15
ms.technology: vs-acquisition
ms.topic: conceptual
author: PoulChapman
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: d4558e086ec53aa0e264fd55a322d4b5acaac7aa
ms.sourcegitcommit: cc88ccc6aacebe497899fab05d243a65053e194c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/23/2018
---
# <a name="visual-studio-customer-experience-improvement-program"></a>Programu zlepšování zkušeností zákazníků v sadě Visual Studio

Visual Studio zákazníka prostředí zlepšování Program (VSCEIP) je program pomáhá společnosti Microsoft zlepšovat Visual Studio v čase. Tento program shromažďuje informace o hardwaru počítače a jak lidé použijte sadu Visual Studio, aniž by to ovlivnilo uživatelům v jejich úlohy v počítači. Shromažďované informace pomáhají společnosti Microsoft určit funkce, které ke zlepšení. Tento dokument popisuje, jak přidat nebo zrušit VSCEIP.

## <a name="opt-in-or-out"></a>OPT příchozí nebo odchozí

VSCEIP je zapnutá ve výchozím nastavení. Můžete ho vypnout, nebo znovu, zpět na podle těchto pokynů:

1. Spuštění sady Visual Studio.

1. Z **pomoci** nabídky, přejděte na příkaz **odeslat zpětnou vazbu**a potom vyberte **nastavení**.

   **Visual Studio programu na zlepšování zkušeností** otevře se dialogové okno.

1. Chcete-li chodit, vyberte **Ne, nebude líbí se zúčastnit**a potom vyberte **OK**.
   Chcete-li vyjádřit výslovný souhlas, vyberte **Ano, chci se zúčastnit**a potom vyberte **OK**.

   ![Visual Studio programu na zlepšování zkušeností dialogové okno](media/experience-improvement-program.png)

### <a name="registry-settings"></a>Nastavení registru

Pokud instalujete [nástroje sestavení pro Visual Studio](https://www.visualstudio.com/downloads/#build-tools-for-visual-studio-2017), je nutné aktualizovat registr a nakonfigurujte VSCEIP. Podnikoví zákazníci můžete vytvořit zásady skupiny pro aktivování nebo zrušení VSCEIP nastavením zásad týkajících se registru.

[!INCLUDE [gdpr-hybrid-note](../misc/includes/gdpr-hybrid-note.md)]

Příslušný klíč registru a nastavení jsou následující:

Klíč = **HKEY_CURRENT_USER\SOFTWARE\Microsoft\VSCommon\15.0\SQM**

Položka = OptIn

Hodnota = (DWORD)
- **0** je používání (vypněte VSCEIP)
- **1** bude poskytnut souhlas (zapněte VSCEIP)

> [!CAUTION]
> Pokud chybně upravíte registr, může dojít k vážnému poškození systému. Před provedením změn v registru doporučujeme zálohovat všechna důležitá data v počítači. Můžete také **poslední známá funkční konfigurace** možnost spuštění, pokud narazíte na potíže po ručně provedených změnách.

Další informace o informacích shromažďovaných, zpracovávaných a přenášených v rámci VSCEIP, najdete v článku [prohlášení o ochraně osobních údajů Microsoft](https://privacy.microsoft.com/privacystatement).

## <a name="see-also"></a>Viz také

* [Kontaktujte nás](../ide/talk-to-us.md)
* [Postup nahlásit problém pomocí sady Visual Studio](../ide/how-to-report-a-problem-with-visual-studio-2017.md)
* [Komunity vývojářů v sadě Visual Studio](https://developercommunity.visualstudio.com/)
* [Prohlášení o ochraně osobních údajů společnosti Microsoft](https://privacy.microsoft.com/privacystatement)