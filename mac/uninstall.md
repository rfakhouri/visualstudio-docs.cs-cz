---
title: Odinstalace Visual Studio pro Mac | Microsoft Docs
description: "Pokyny k odinstalaci Visual Studio pro Mac a související nástroje."
author: asb3993
ms.author: amburns
ms.date: 04/14/2017
ms.topic: article
ms.technology: vs-ide-install
ms.assetid: 4EB95F75-BC2E-4982-9564-2975805712D8
ms.openlocfilehash: 193856ca96395db9a5b3bd494a5b8f1f7331f702
ms.sourcegitcommit: 238cd48787391aa0ed1eb684f3f04e80f7958705
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/12/2018
---
# <a name="uninstalling-visual-studio-for-mac"></a>Odinstalace Visual Studio pro Mac

Existuje řada produktů Xamarin, které umožňují vývoj aplikací pro různé platformy, včetně samostatné aplikace, jako je Visual Studio for Mac.

Tato příručka slouží k odinstalaci každý produkt jednotlivě tak, že přejdete do části relevantní. Celá sada nástrojů Xamarin, můžou se odinstalovat podle této příručky úplně prostřednictvím.

Pokud jste dřív měli Xamarin Studio v počítači nainstalován, budete možná muset taky postupujte podle pokynů v [odinstalovat](https://developer.xamarin.com/guides/cross-platform/getting_started/installation/uninstalling_xamarin/) Průvodce na developer.xamarin.com, kromě následující kroky.

## <a name="uninstall-script"></a>Odinstalujte skriptu

Odinstalujete Visual Studio a jeho přidružených součásti v jednom přejít pomocí [odinstalovat skriptu](https://raw.githubusercontent.com/MicrosoftDocs/visualstudio-docs/master/mac/resources/uninstall-vsmac.sh).

Tento skript odinstalovat obsahuje většinu příkazů, které najdete v článku. Existují dvě hlavní opomenutí ze skriptu a nejsou zahrnuty z důvodu možných externí závislosti:

- **Odinstalace Mono**
- **Odinstalace Android AVD**

Chcete-li spustit skript, proveďte následující kroky:

1. Klikněte pravým tlačítkem na skript a vyberte **uložit jako...** Uložte soubor na vašem Mac.
2. Otevřete terminál a změnit pracovní adresář, do které jste stáhli skript:

    ```bash
    $ cd /location/of/file
    ```
3. Spustitelný soubor skriptu a spustit ji s **sudo**:

    ```bash
    $ chmod +x ./uninstall-vsmac.sh
    $ sudo ./uninstall-vsmac.sh
    ```
4. Nakonec odstraňte odinstalační skript.

## <a name="uninstall-visual-studio-for-mac"></a>Odinstalace Visual Studio pro Mac

Prvním krokem při odinstalaci Visual Studio z algoritmu Mac, je nalezení **Visual Studio.app** v **/Applications** adresáře a přetáhněte ji do **odpadkový koš**. Případně, klikněte pravým tlačítkem a vyberte **přesunout do Koš** jak je znázorněno na následujícím obrázku:

![Přesunutí aplikace Visual Studio koše](media/uninstall-image1.png)

Visual Studio pro Mac, odstraněním této sady prostředků aplikace odebere, i když může být další soubory týkající se Xamarin stále v systému souborů.

K odebrání všech trasování sady Visual Studio pro Mac, by měl v terminálu spustit následující příkazy:

```bash
sudo rm -rf "/Applications/Visual Studio.app"
rm -rf ~/Library/Caches/VisualStudio
rm -rf ~/Library/Preferences/VisualStudio
rm -rf ~/Library/Preferences/Visual\ Studio
rm -rf ~/Library/Logs/VisualStudio
rm -rf ~/Library/VisualStudio
rm -rf ~/Library/Preferences/Xamarin/
rm -rf ~/Library/Developer/Xamarin
rm -rf ~/Library/Application\ Support/VisualStudio
rm -rf ~/Library/Application\ Support/VisualStudio/7.0/LocalInstall/Addins/
```

## <a name="uninstall-mono-sdk-mdk"></a>Odinstalujte Mono SDK (MDK)

Mono je implementací open-source společnosti Microsoft .NET Framework a umožňuje Xamarin Products—Xamarin.iOS, Xamarin.Android a Xamarin.Mac vývoj těchto platforem v jazyce C#.

> [!WARNING]
> Existují další aplikace mimo Visual Studio pro Mac kteří také používají Mono, jako je například Unity.
> Ujistěte se, že neexistují žádné další závislosti na Mono před odinstalací jej.

Rozhraní Framework Mono odebrat z počítače, spusťte následující příkazy v terminálu:

```bash
sudo rm -rf /Library/Frameworks/Mono.framework
sudo pkgutil --forget com.xamarin.mono-MDK.pkg
sudo rm -rf /etc/paths.d/mono-commands
```

## <a name="uninstall-xamarinandroid"></a>Odinstalace Xamarin.Android

Existuje několik položek, které jsou potřebné pro instalaci a použití Xamarin.Android, jako je například Android SDK a sadu Java SDK.

Chcete-li odebrat Xamarin.Android použijte následující příkazy:

```bash
sudo rm -rf /Developer/MonoDroid
rm -rf ~/Library/MonoAndroid
sudo pkgutil --forget com.xamarin.android.pkg
sudo rm -rf /Library/Frameworks/Xamarin.Android.framework
```

### <a name="uninstall-android-sdk-and-java-sdk"></a>Odinstalování SDK pro Android SDK a Java

Je vyžadována pro vývoj aplikací pro Android SDK pro Android. Pokud chcete úplně odebrat všechny části sady SDK pro Android, vyhledejte soubor v **~/Library/Developer/Xamarin/** a přesunout ji do **Koš**.

Java SDK (JDK) není nutné odinstalovat, protože je již předběžně zabalen jako součást systému Mac OS X nebo systému macOS.

### <a name="uninstall-android-avd"></a>Odinstalujte Android AVD

> [!WARNING]
> Existují další aplikace mimo Visual Studio pro Mac kteří také používají Android AVD a tyto další android součásti, jako je například Android Studio.
> Odebrání tento adresář může způsobit, že projekty pro přerušení v Android Studio. 

Chcete-li odebrat všechny Android AVDs a další Android součásti použijte následující příkaz:

```bash
rm -rf ~/.android
```

Chcete-li odebrat pouze Android AVDs použijte následující příkaz:

```bash
rm -rf ~/.android/avd
```

 

## <a name="uninstall-xamarinios"></a>Odinstalace Xamarin.iOS

Xamarin.iOS umožňuje iOS vývoj aplikací pomocí jazyka C# nebo F # pomocí sady Visual Studio for Mac.

Použijte následující příkazy v terminálu odebere všechny soubory Xamarin.iOS systému souborů:

```bash
rm -rf ~/Library/MonoTouch
sudo rm -rf /Library/Frameworks/Xamarin.iOS.framework
sudo rm -rf /Developer/MonoTouch
sudo pkgutil --forget com.xamarin.monotouch.pkg
sudo pkgutil --forget com.xamarin.xamarin-ios-build-host.pkg
sudo pkgutil --forget com.xamarin.xamarin.ios.pkg
```

## <a name="uninstall-xamarinmac"></a>Odinstalace Xamarin.Mac

Xamarin.Mac může být odstraněn z počítače pomocí následujících příkazů pro eradikaci produktu a licenci pro počítače Mac v uvedeném pořadí:

```bash
sudo rm -rf /Library/Frameworks/Xamarin.Mac.framework
rm -rf ~/Library/Xamarin.Mac
```

## <a name="uninstall-workbooks-and-inspector"></a>Odinstalujte sešitů a Inspector

Počínaje 1.2.2, Xamarin sešity & Kontrola můžou se odinstalovat z terminálu spuštěním:

```bash
sudo /Library/Frameworks/Xamarin.Interactive.framework/Versions/Current/uninstall
```

Pro starší verze budete muset ručně odstranit následující artefakty:

* Odstranit aplikaci sešity v`"/Applications/Xamarin Workbooks.app"`
* Odstranit aplikaci Inspector ve`"Applications/Xamarin Inspector.app"`
* Odstranit doplňky: `"~/Library/Application Support/XamarinStudio-6.0/LocalInstall/Addins/Xamarin.Interactive"` a`"~/Library/Application Support/XamarinStudio-6.0/LocalInstall/Addins/Xamarin.Inspector"`
* Odstraňte Inspector a podpůrné soubory. zde: `/Library/Frameworks/Xamarin.Interactive.framework` a`/Library/Frameworks/Xamarin.Inspector.framework`

# <a name="uninstall-the-xamarin-profiler"></a>Odinstalace Xamarin profileru

```bash
sudo rm -rf "/Applications/Xamarin Profiler.app"
```

## <a name="uninstall-the-visual-studio-installer"></a>Odinstalujte instalační program sady Visual Studio

K odebrání všech trasování Xamarin Universal instalačního programu, použijte následující příkazy:

```bash
rm -rf ~/Library/Caches/XamarinInstaller/
rm -rf ~/Library/Caches/VisualStudioInstaller/
rm -rf ~/Library/Logs/XamarinInstaller/
rm -rf ~/Library/Logs/VisualStudioInstaller/
rm -rf ~/Library/Preferences/Xamarin/
rm -rf "~/Library/Preferences/Visual Studio/"
```
