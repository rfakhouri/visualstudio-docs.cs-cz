---
title: Správa přidružení souborů vedle sebe | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- verbs, setting default
ms.assetid: 9b6df3bc-d15c-4a5d-9015-948a806193b7
caps.latest.revision: 18
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: b8ca68aec180c51a170fd6ecce58237a5b306705
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68194391"
---
# <a name="managing-side-by-side-file-associations"></a>Správa přidružení souborů vedle sebe

[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Pokud vaše VSPackage poskytuje přidružení souborů, musíte rozhodnout, jak zpracovat-souběžnými instalacemi, ve kterém konkrétní verzi [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] by mělo být vyvoláno pro otevření souboru. Formáty souborů složené problém.

Uživatelé očekávají, že nová verze produkt, který má být kompatibilní s předchozími verzemi, takže je možné načíst existující soubory v nové verzi bez ztráty dat. V ideálním případě by vaše VSPackage můžete načíst i uložit formáty souborů starších verzí. Pokud to není pravda, byste měli nabízet k upgradu na formát souboru na novou verzi vašeho balíčku VSPackage. Nevýhodou tohoto přístupu je, že upgradovaný soubor nelze otevřít v dřívější verzi.

K tomuto problému vyhnout, můžete změnit rozšíření při formáty souborů přestala být kompatibilní. Například verze 1 vašeho balíčku VSPackage použít rozšíření, .mypkg10 a verze 2 může používat rozšíření, .mypkg20. Tento rozdíl identifikuje sady VSPackage, která otevírá určitý soubor. Pokud přidáte do seznamu programů, které jsou spojeny s původní příponou novější rozšíření VSPackages, můžou uživatelé klikněte pravým tlačítkem na soubor a zvolte Otevřít v novější VSPackage. V tomto okamžiku může nabídnout soubor upgradovat na nový formát nebo otevřete soubor a udržovat kompatibilitu s předchozími verzemi sady VSPackage vašeho balíčku VSPackage.

> [!NOTE]
> Tyto přístupy můžete kombinovat. Můžete například nabídka zpětné kompatibility při načítání starší souboru a nabídnout k upgradu na formát souboru, když uživatel uloží ho.

## <a name="facing-the-problem"></a>Směřující problému

Pokud chcete, aby více rozšíření VSPackages vedle sebe používat stejnou příponu, je třeba zvolit verzi [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] přidružený k rozšíření. Tady jsou dvě možnosti:

- Otevřete soubor v nejnovější verzi [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] nainstalovaná na počítači uživatele.

   V takovém případě je instalačním programem vaší odpovědností nejnovější verzi [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] a včetně, která v registru napsané pro přidružení souboru. V balíčku Instalační služby systému Windows, můžete zahrnout vlastní akce nastavení vlastnosti, která určuje nejnovější verzi [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].

  > [!NOTE]
  > V tomto kontextu se toto "posledního" znamená "nejnovější podporovanou verzi." Tyto položky Instalační program automaticky nerozpozná následné verze služby [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Položky v [zjišťování požadavky na systém](../extensibility/internals/detecting-system-requirements.md) a [příkazy, musí být spustit po instalaci](../extensibility/internals/commands-that-must-be-run-after-installation.md) jsou podobné těm, které jsou uvedeny v tomto tématu a jsou vyžadovány pro podporu dalších verzích [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].

   Následující řádky v tabulce CustomAction nastavit DEVENV_EXE_LATEST vlastnost, která má být vlastnost nastavit AppSearch a tabulky RegLocator popsaných v [příkazy, musí být spustit po instalaci](../extensibility/internals/commands-that-must-be-run-after-installation.md). Řádky v tabulce InstallExecuteSequence naplánovat vlastní akce již v rané fázi v pořadí spouštění. Hodnoty ve sloupci zkontrolujte podmínku logiku fungují:

  - Visual Studio .NET 2002 má nejnovější verzi, pokud se jedná pouze aktuální verze.

  - Visual Studio .NET 2003 má nejnovější verzi, pouze pokud je k dispozici a [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] není k dispozici.

  - [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Pokud se jedná pouze aktuální verze má nejnovější verzi.

    Net výsledkem je, že DEVENV_EXE_LATEST obsahuje cestu k nejnovější verzi devenv.exe.

  **CustomAction řádky tabulky, které určují nejnovější verzi sady Visual Studio**

  |Akce|type|Source|Target|
  |------------|----------|------------|------------|
  |CA_SetDevenvLatest_2002|51|DEVENV_EXE_LATEST|[DEVENV_EXE_2002]|
  |CA_SetDevenvLatest_2003|51|DEVENV_EXE_LATEST|[DEVENV_EXE_2003]|
  |CA_SetDevenvLatest_2005|51|DEVENV_EXE_LATEST|[DEVENV_EXE_2005]|

  **InstallExecuteSequence řádky tabulky, které určují nejnovější verzi sady Visual Studio**

  |Akce|Podmínka|Sequence|
  |------------|---------------|--------------|
  |CA_SetDevenvLatest_2002|DEVENV_EXE_2002 A NENÍ (DEVENV_EXE_2003 NEBO DEVENV_EXE_2005)|410|
  |CA_SetDevenvLatest_2003|DEVENV_EXE_2003 A NE DEVENV_EXE_2005|420|
  |CA_SetDevenvLatest_2005|DEVENV_EXE_2005|430|

   Vlastnost DEVENV_EXE_LATEST v tabulce registru balíček Instalační služby systému Windows můžete použít k zápisu HKEY_CLASSES_ROOT*ProgId*ShellOpenCommand klíč výchozí hodnotu [DEVENV_EXE_LATEST] "%1"

- Spusťte program sdílené spouštěcí program, který může být nejlepší volbou z dostupných verzí balíčku VSPackage.

   Vývojáři [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] vybrali tento přístup ke zpracování složité požadavky více formátů řešení a projektů, které jsou výsledkem mnoho verzí [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. V takovém případě spouštěcího programu zaregistrovat jako obslužná rutina rozšíření. Spouštěč zkontroluje tento soubor a rozhodne, kterou verzi [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] a vaše VSPackage dokáže zpracovat tuto konkrétní soubor. Například pokud uživatel otevře soubor, který byl naposledy uložil konkrétní verzi vašeho balíčku VSPackage, Spouštěč můžete spustit tento VSPackage v odpovídající verzi [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Kromě toho může uživatel nakonfigurovat Spouštěč vždy spustit na nejnovější verzi. Spouštěč také může vyzvat uživatele k upgradu na formát souboru. Pokud formát souboru obsahuje číslo verze, Spouštěč může informovat uživatele, pokud je formát souboru z verze, která je novější než jeden nebo více nainstalovaných rozšíření VSPackages.

   Spouštěč musí být v komponentě Instalační služby systému Windows, který je sdílen se všemi verzemi vašeho balíčku VSPackage. Tento proces zajišťuje, že nejnovější verze je vždy nainstalován a neodeberou, dokud se odinstalovat všechny verze vašeho balíčku VSPackage. Tímto způsobem jsou zachovány přidružení souborů a dalších položek registru součásti Spouštěč i v případě, že jednu verzi sady VSPackage se odinstaluje.

## <a name="uninstall-and-file-associations"></a>Odinstalujte a přidružení souborů

Odinstalace balíčku VSPackage, která zapisuje položky registru pro přidružení typu souboru odebere přidružení souborů. Proto že rozšíření má žádné přidružené programy. Instalační služby systému Windows není "obnovit" položky registru, které byly přidány při instalaci sady VSPackage. Tady jsou některé způsoby, jak vyřešit přidružení souborů uživatele:

- Použijte sdílené Spouštěč komponentu, jak je uvedeno výše.

- Pokyny pro uživatele, chcete-li spustit opravu verze sady VSPackage, která chce uživatel vlastní přidružení souboru.

- Zadejte samostatný spustitelný program, který přepíše položky registru.

- Zadejte konfigurační možnosti stránky nebo dialogové okno pole, která umožňuje uživatelům zvolit přidružení souborů a získat zpět ke ztrátě přidružení. Dáte pokyn, aby uživatelé spouštěli po odinstalaci.

## <a name="see-also"></a>Viz také

[Registrace přípony názvů souborů pro nasazení vedle sebe](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)
[registrace operací pro přípony názvů souborů](../extensibility/registering-verbs-for-file-name-extensions.md)
