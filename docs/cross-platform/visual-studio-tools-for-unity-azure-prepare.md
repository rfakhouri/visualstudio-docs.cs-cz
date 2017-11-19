---
title: "Visual Studio Tools for Unity Příprava Azure návod | Microsoft Docs"
ms.custom: 
ms.date: 10/19/2017
ms.reviewer: crdun
ms.suite: 
ms.technology: tgt-pltfrm-cross-plat
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: B921C2AC-B5D6-4B24-918E-511F83D57275
author: dantogno
ms.author: v-davian
manager: crdun
ms.openlocfilehash: 92f85e39d0f643e896457cae48ab10aa0446dfcd
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/09/2017
---
# <a name="prepare-the-development-environment"></a>Příprava vývojového prostředí

Existují některé požadavky pomocí Azure Mobile Client SDK v Unity.

## <a name="download-and-install-unity-2017"></a>Stáhněte a nainstalujte Unity 2017

Unity 2017.1 nebo vyšší se vyžaduje. Všechny plány Unity pracovat návod, včetně osobních plánu úrovně free. Stáhněte si Unity z https://store.unity.com/.

## <a name="download-and-install-visual-studio-2017"></a>Stáhněte a nainstalujte Visual Studio 2017

Průvodce vyžaduje Visual Studio 2017 15.3 a vyšší, s vývoj her Unity zatížení. Všechny edice Visual Studio 2017 pracovat návod, včetně bezplatná edice Community.

1. Stáhněte si Visual Studio 2017 v https://www.visualstudio.com/.

2. Instalace Visual Studio 2017 a ujistěte se, že **her vývoj s Unity** zatížení je povoleno.

 ![Výběr úlohy Unity](media/vstu_azure-prepare-dev-environment-image0.png)

 > [!NOTE]
 > Pokud Visual Studio 2017 je již nainstalován, můžete zobrazit a upravit úlohy tak, že spustíte instalační program Visual Studio.

## <a name="create-a-new-3d-unity-project"></a>Vytvoření nového projektu 3D Unity

Spusťte Unity a vytvořte nový projekt 3D.

![Vytvoření nového projektu Unity](media/vstu_azure-prepare-dev-environment-image1.png)

## <a name="set-the-script-editor-to-visual-studio-preview-2017"></a>Nastavit editor skriptů na Visual Studio Preview 2017

Je vybrán jeho možné, že již máte Visual Studio 2017 nastavit jako editor externího skriptu pro Unity, ale je důležité zajistit 15.3 verzi Preview.

1. Z Unity **upravit** nabídce zvolte **Upravit > Předvolby...** .

  ![Otevřete nabídku předvolby](media/vstu_azure-prepare-dev-environment-image1.2.png)

2. Pokud okno Předvolby Unity objeví, vyberte **externích nástrojů** karty na levé straně.

3. V **Editor skriptů externí** rozevírací nabídce vyberte **Visual Studio 2017**.

  ![Sada externího skriptu editoru](media/vstu_azure-prepare-dev-environment-image3.png)

## <a name="change-the-unity-scripting-runtime-to-net-46"></a>Změňte Unity skriptování modulu runtime .NET 4.6
Průvodce vyžaduje rozhraní .NET 4.6-li používat Azure Mobile Client SDK a jeho závislosti.

1. Z Unity **soubor** nabídce zvolte **soubor > Nastavení sestavení...** .

  ![Otevřete nastavení sestavení](media/vstu_azure-prepare-dev-environment-image4.png)

2. Klikněte **Player nastavení...**  tlačítko.

  ![Otevřete nastavení player](media/vstu_azure-prepare-dev-environment-image5.png)

3. Nastavení Player otevře v okně Unity kontroly. V části **konfigurace** záhlaví, klikněte na tlačítko **skriptování verzi modulu Runtime** rozevírací seznam a vyberte **experimentální (.NET 4.6 ekvivalentní)**. Zobrazí se výzva zobrazí se dialogové okno s dotazem, restartovat Unity. Vyberte **restartujte**.

  ![Vyberte .NET 4.6](media/vstu_azure-prepare-dev-environment-image6.png)

## <a name="add-a-reference-to-systemnethttpdll"></a>Přidat odkaz na System.Net.Http.dll

Modul runtime rozhraní .NET 4.6 Unity ekvivalentní skriptování umožňuje používat System.Net.Http balíčku, který je vyžadován součástí sady Azure Mobile klienta SDK. Soubor knihovny DLL je součástí Unity, ale odkaz musí být přidaný do ho použít.

1. V okně editoru pro projekt Unity **klikněte pravým tlačítkem na** **prostředky** složky a vyberte **zobrazit v Průzkumníku**.

  ![Zobrazit v Průzkumníku prostředků složky](media/vstu_azure-prepare-dev-environment-image7.png)

2. V okně Průzkumníka, která se objeví, dvakrát klikněte **prostředky** directory ho otevřete.

3. V adresáři prostředky **klikněte pravým tlačítkem na** a vyberte **nový > textový dokument**.

4. Otevřete nový textový dokument v textovém editoru a přidejte řádek:`-r:System.Net.Http.dll`

5. Uložte dokument a zavřete.

4. Přejmenujte nový textový dokument k "**mcs.rsp**" a nezapomeňte odstranit příponu .txt.

  * Pokud máte přípony souborů skryté, bude muset změnit možnosti zobrazení složky je chcete zobrazit.
  * Otevřete nabídku a typu "složky možnosti spuštění" pro vyhledávání. Vyberte "**souboru možnosti Explorer**".
  * Vyberte **zobrazení** kartě a ujistěte se, v části Upřesnit nastavení "**Skrýt příponu souborů známých typů**" není zaškrtnuta.

    ![Zobrazit v Průzkumníku prostředků složky](media/vstu_azure-prepare-dev-environment-image8.png)

Po dokončení těchto kroků byste měli mít soubor s názvem **mcs.rsp** řádek `r:System.Net.Http.dll` v kořenovém adresáři projektu Unity **prostředky** adresáře.

>[!NOTE]
> Referenční dokumentace funkcí vyžaduje Visual Studio Tools pro Unity 3.3 a výše, která je zahrnutá v sadě Visual Studio 15.3 + Unity zatížení. Pokud tento krok nefunguje pro vás, ujistěte se, že máte správnou verzi VSTU nainstalována.

## <a name="add-the-newtonsoftjson-nuget-package-to-your-project"></a>Do projektu přidejte balíček Newtonsoft.Json NuGet

Azure Mobile Client SDK vyžaduje balíček Newtonsoft.Json. Unity bohužel nepodporuje NuGet. Pokud otevřete Unity projektu v sadě Visual Studio a přidejte balíček NuGet, Unity vymaže ji při příštím otevřete projekt v editoru Unity. Však balíčky NuGet můžete ručně přidat do projektu Unity.

1. Vytvořte novou složku v projektu Unity prostředky adresář s názvem "**balíčky NuGet**". Toto je pouze organizace.

2. Přejděte do https://www.nuget.org/packages/Newtonsoft.Json/ a kliknutím **ruční stažení** tlačítko. Stažení souboru .nupkg v podadresáři.

  ![Zobrazit v Průzkumníku prostředků složky](media/vstu_azure-prepare-dev-environment-image9.png)

3. Vyhledejte nově stažený soubor a změňte příponu souboru z .nupkg k **.zip**. To by vám mělo umožnit zobrazit a extrahovat zahrnuté soubory jako jakýkoli jiný soubor zip.

4. Otevřete nebo extrahování adresáře zip a přejděte do **\lib\net45**.

5. Kopírování **Newtonsoft.Json.dll** souboru do projektu Unity **Assets\NuGet balíčky** adresáře.

## <a name="add-the-azure-mobile-client-sdk-nuget-package-to-your-project"></a>Přidejte balíček Azure Mobile klienta SDK NuGet do projektu

Azure Mobile Client SDK obsahuje funkce pro snadné čtení a zápis do snadno tabulky Azure.

1. Přejděte do https://www.nuget.org/packages/Microsoft.Azure.Mobile.Client/ a kliknutím **ruční stažení** tlačítko. Stažení souboru .nupkg v podadresáři.

2. Vyhledejte nově stažený soubor a změňte příponu souboru z .nupkg k **.zip**. To by vám mělo umožnit zobrazit a extrahovat zahrnuté soubory jako jakýkoli jiný soubor zip.

3. Otevřete nebo extrahování adresáře zip a přejděte do **\lib\net45**.

4. Kopírování **Microsoft.Azure.Mobile.Client.dll** souboru do projektu Unity **Assets\NuGet balíčky** adresáře.

>[!WARNING]
> Po dokončení těchto kroků, nezapomeňte restartovat Unity a Visual Studio nebo InteliSense nemusí rozpoznat nově přidané balíčky.

## <a name="conclusion"></a>Závěr

Po dokončení těchto kroků, by měla být projektu Unity pomocí Azure Mobile Client SDK instalačního programu. Vytvořením nový skript jazyka C# ve vašem projektu Unity, ho otevřít v sadě Visual Studio a zadáním následujícího příkazu můžete otestovat vývojového prostředí pomocí příkazů v horní části:
```
using System.Net.Http;
using Newtonsoft.Json;
using Microsoft.WindowsAzure.MobileServices;
```

Pokud InteliSense zjistí tyto příkazy, instalace byla dokončena správně. Pokud nejsou žádné chyby nebo InteliSense nerozpoznává tyto balíčky, zkuste restartovat Unity a Visual Studio. Pokud stále nefunguje, pokroku výše uvedených kroků.

## <a name="next-step"></a>Další krok

* [Vytvořit datové třídy modelu](visual-studio-tools-for-unity-azure-data.md)
