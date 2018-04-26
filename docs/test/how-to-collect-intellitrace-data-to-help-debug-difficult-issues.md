---
title: Dat technologie Intellitrace v sadě Visual Studio
ms.date: 10/13/2016
ms.topic: conceptual
helpviewer_keywords:
- IntelliTrace, configuring test settings
- Diagnostic Data Adapter, InteliTrace
- debugging [Visual Studio ALM], difficult issues using IntelliTrace
- Test Runner, InteliTrace
ms.assetid: 02b6716f-569e-4961-938a-e790a0c74b5c
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.openlocfilehash: c6b34993e011a8bf539b6ec2dd70beddf9c96caf
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-collect-intellitrace-data-to-help-debug-difficult-issues"></a>Postupy: Shromáždění dat technologie IntelliTrace pro snazší ladění složitých problémů

Adaptér diagnostických dat pro technologii IntelliTrace shromažďovat informace o konkrétní diagnostické trasování v Visual Stdio můžete nakonfigurovat. Testy mohou tento adaptér používat. Test může shromažďovat podstatné diagnostické události aplikace, které může vývojář později použít pro trasování skrze kód a nalezení příčiny chyby. Adaptér diagnostiky dat pro technologii IntelliTrace lze použít pro manuální, nebo automatizované testy.

> [!NOTE]
> Technologie IntelliTrace pracuje pouze v aplikaci, která je napsána ve spravovaném kódu. Pokud testujete webovou aplikaci, která jako klienta používá prohlížeč, neměli byste v nastaveních testů povolit pro klienta technologii IntelliTrace, protože pro trasování není k dispozici žádný spravovaný kód. V tomto případě lze nastavit prostředí a shromažďovat data IntelliTrace vzdáleně na webovém serveru.

Data IntelliTrace jsou uložena v souboru, který má příponu .iTrace. Když spustíte test a test krok nezdaří, můžete vytvořit chyby. Soubor IntelliTrace, který obsahuje diagnostické informace, je automaticky připojen k této chybě.

> [!NOTE]
> Adaptér diagnostiky dat pro technologii IntelliTrace nevytvoří soubor IntelliTrace, pokud test proběhne úspěšně. Soubor se uloží pouze při selhání testovacího případu nebo při odeslání hlášení o chybě.

 Data shromažďovaná do souboru IntelliTrace zvyšují efektivitu ladění zkrácením doby potřebné k reprodukci a diagnostice chyby v kódu. Navíc vzhledem k tomu, že soubor IntelliTrace lze sdílet s jinou osobou, která může replikovat místní relaci ve svém počítači, se snižuje pravděpodobnost, že chyby nebudou reprodukovatelné.

> [!NOTE]
> Pokud v nastaveních testů povolíte technologii IntelliTrace, nebude fungovat shromažďování dat o pokrytí kódu.

> [!WARNING]
> Adaptér diagnostiky dat pro technologii IntelliTrace funguje díky instrumentaci spravovaného procesu, která musí být provedena po načtení testů pro testovací běh. Pokud již byl proces, který chcete sledovat, spuštěn, nebudou shromážděny žádné soubory IntelliTrace, protože proces již probíhá. To lze obejít ověřením, že se proces před načtením testů ukončil. Poté po načtení testů nebo spuštění prvního testu spusťte proces.

 Následující postup popisuje, jak nakonfigurovat data IntelliTrace, která chcete shromažďovat. Tento postup platí pro editor konfigurací v nástroji Microsoft Test Manager a testovací nastavení dialogové okno v sadě Visual Studio.

> [!NOTE]
> Uživatelský účet pro testovacího agenta, který je používán k shromažďování dat IntelliTrace, musí být členem skupiny administrátorů. Další informace najdete v tématu [instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md).

## <a name="configure-the-data-to-collect-with-the-intellitrace-diagnostic-data-adapter"></a>Konfigurace dat pro shromažďování dat prostřednictvím adaptéru diagnostiky dat technologie IntelliTrace

Před provedením kroků v tomto postupu, je nutné otevřít nastavení testu z Microsoft Test Manager nebo Visual Studio a vybrat **datové a diagnostické** stránky.

### <a name="to-configure-the-data-to-collect-with-the-intellitrace-diagnostic-data-adapter"></a>Konfigurace dat pro shromažďování dat prostřednictvím adaptéru diagnostiky dat technologie IntelliTrace

1.  Vyberte roli, kterou chcete použít pro shromažďování dat IntelliTrace.

2.  Vyberte **IntelliTrace**.

3.  Pokud přidáváte IntelliTrace pro webové role klienta nebo pro webovou aplikaci ASP.NET, je nutné vybrat také **proxy server klienta ASP.NET pro IntelliTrace a dopadu testu**.

     Tento proxy klient umožňuje shromažďovat informace o http voláních z klienta na webový server pro adaptéry diagnostiky dat technologie IntelliTrace a dopadu testu.

    > [!WARNING]
    > Pokud se rozhodnete použít vlastní účet pro identitu, která je používána pro fond aplikací na serveru služby IIS, kde máte v úmyslu shromažďovat data Intellitrace, je třeba vytvořit místní profil uživatele v počítači služby IIS pro vlastní účet, který je používán. Místní profil lze pro vlastní účet vytvořit jednorázovým přihlášením na počítači se službou IIS místně, nebo spuštěním následujícího příkazu příkazového řádku pomocí vlastních pověření účtu:
    >
    > **runas /user:domain\name /profile cmd.exe**

4.  Zvolte **konfigurace** pro **IntelliTrace** upravovat výchozí nastavení IntelliTrace.

     Zobrazí se dialogové okno pro konfiguraci dat, která budou shromažďována.

    > [!WARNING]
    > Pokud povolíte shromažďování dat IntelliTrace, nebude fungovat shromažďování dat pokrytí kódu.

5.  Vyberte **Obecné** kartě. Vyberte **pouze události IntelliTrace** k zaznamenání významné diagnostických událostí, které mají minimální dopad na výkon při testování.

     **-** nebo –

     Vyberte **události IntelliTrace a volání informace** k zaznamenání diagnostických událostí a metoda úroveň trasování, který zobrazuje informace o volání. Tato úroveň trasování může mít vliv na výkon při spuštění testů.

6.  Chcete-li shromažďovat data z vaší aplikace ASP.NET, která běží na Internetové informační služby, vyberte **shromažďovat data z aplikace ASP.NET, které jsou spuštěny v Internetové informační služby**. Nastavte a nakonfigurujte testovacího agenta v roli webového serveru. V tématu [instalace a konfigurace testovacích agentů](../test/lab-management/install-configure-test-agents.md).

7.  Vyberte **moduly** kartě. Vyberte buď **shromažďování dat ze všech modulů s výjimkou následujících** a používat **přidat** přidat do seznamu modulů a **odebrat** odebrat modul. Tato volba umožňuje zahrnout všechny moduly, které jsou spuštěny v systému kromě modulů, jež zadáte.

     -nebo-

     Vyberte **shromažďovat data z jenom následující moduly** a používat **přidat** přidat do seznamu modulů a **odebrat** odebrat modul. Tato volba umožňuje přesně určit požadované moduly.

    > [!NOTE]
    > Pokud je to možné, vyberte konkrétní postupy, které chcete sledovat. To je doporučeno pro optimální výkon.

8.  Vyberte **procesy** kartě. Vyberte **shromažďování dat ze všech procesů, s výjimkou následujících** a používat **přidat** přidat do seznamu procesů a **odebrat** odebrat proces. Tato volba umožňuje zahrnout všechny procesy, které jsou spuštěny v systému kromě procesů, jež zadáte.

     -nebo-

     Vyberte **shromažďovat data ze zadaného procesy pouze** a používat **přidat** přidat do seznamu procesů a **odebrat** odebrat proces. Tato volba umožňuje přesně určit požadované procesy.

9. (Volitelné) Vyberte **události IntelliTrace** kartě. Zaškrtněte nebo zrušte zaškrtnutí jednotlivých kategorií událostí IntelliTrace, které chcete zahrnout nebo vyloučit při shromažďování diagnostických událostí.

10. (Volitelné) Rozbalte každou kategorii událostí IntelliTrace a zaškrtněte nebo zrušte zaškrtnutí každé konkrétní události, kterou chcete zahrnout nebo vyloučit v událostech IntelliTrace.

11. (Volitelné) Vyberte **Upřesnit** kartě. V dalším kroku vyberte šipku vedle **maximální množství místa na disku pro záznam** a vyberte maximální velikost, kterou chcete povolit pro tento soubor IntelliTrace.

    > [!NOTE]
    > Pokud velikost pro záznam zvětšíte, může dojít k problému s vypršením času při ukládání tohoto záznamu společně s výsledky testů. Další informace o způsobu zvýšení hodnoty časového limitu pro adaptérů diagnostických dat najdete v tématu [postupy: zabránění vypršení časových limitů u adaptérů diagnostických dat](../test/how-to-prevent-time-outs-for-diagnostic-data-adapters.md).

12. Pokud používáte nástroje Microsoft Test Manager, zvolte **Uložit**. Pokud používáte Visual Studio, vyberte **OK**. Nastavení technologie IntelliTrace je nyní nakonfigurováno a uloženo pro nastavení testů.

    > [!NOTE]
    > Chcete-li obnovit konfiguraci pro tento adaptér diagnostických dat, zvolte **resetovat na výchozí konfiguraci** pro sadu Visual Studio nebo **obnovit výchozí** nástroje Microsoft Test Manager.

## <a name="see-also"></a>Viz také

- [Shromažďování diagnostických dat při testování (VSTS)](/vsts/manual-test/collect-diagnostic-data)
- [Shromažďování diagnostických dat v manuálních testech (VSTS)](/vsts/manual-test/mtm/collect-more-diagnostic-data-in-manual-tests)
- [Shromažďování diagnostických informací s použitím nastavení testu](../test/collect-diagnostic-information-using-test-settings.md)
- [Shromažďování dat IntelliTrace](../test/how-to-collect-intellitrace-data-to-help-debug-difficult-issues.md)