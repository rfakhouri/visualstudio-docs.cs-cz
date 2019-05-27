---
title: Zápis do Store nastavení uživatele | Dokumentace Microsoftu
ms.date: 05/23/2019
ms.topic: conceptual
ms.assetid: efd27f00-7fe5-45f8-9b97-371af732be97
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fe8187fe11f4818433aed847a7bc67d4a889ad3a
ms.sourcegitcommit: 19ec963ed6d585719cb83ba677434ea6580e0d1f
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/24/2019
ms.locfileid: "66206886"
---
# <a name="writing-to-the-user-settings-store"></a>Zápis do úložiště uživatelských nastavení
Uživatelská nastavení jsou zapisovatelné nastavení, jako je v **Nástroje / možnosti** dialogového okna, okna vlastností a některých dalších dialogových oknech. Rozšíření sady Visual Studio může použít k ukládání malé množství dat. Tento návod ukazuje, jak přidat program Poznámkový blok se sadou Visual Studio jako externího nástroje ve čtení a zápisu do úložiště uživatelských nastavení.

## <a name="writing-to-the-user-settings-store"></a>Zápis do úložiště uživatelských nastavení

1. Vytvořte projekt VSIX s názvem UserSettingsStoreExtension a pak přidejte vlastní příkaz s názvem UserSettingsStoreCommand. Další informace o tom, jak vytvořit vlastní příkaz najdete v tématu [vytváření rozšíření pomocí příkazu nabídky](../extensibility/creating-an-extension-with-a-menu-command.md)

2. V souboru UserSettingsStoreCommand.cs, přidejte následující příkazy using:

    ```csharp
    using System.Collections.Generic;
    using Microsoft.VisualStudio.Settings;
    using Microsoft.VisualStudio.Shell.Settings;
    ```

3. V MenuItemCallback odstraňte tělo metody a získat uživatelské nastavení uložená, následujícím způsobem:

    ```csharp
    private void MenuItemCallback(object sender, EventArgs e)
    {
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);
        WritableSettingsStore userSettingsStore = settingsManager.GetWritableSettingsStore(SettingsScope.UserSettings);
    }
    ```

4. Teď zjistěte, zda poznámkového bloku již nastaven jako externího nástroje. Je nutné iterovat všechny externí nástroje pro zjištění nastavení ToolCmd "Poznámkový blok", následujícím způsobem:

    ```csharp
    private void MenuItemCallback(object sender, EventArgs e)
    {
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);
        WritableSettingsStore userSettingsStore = settingsManager.GetWritableSettingsStore(SettingsScope.UserSettings);

        // Find out whether Notepad is already an External Tool.
        int toolCount = userSettingsStore.GetInt32("External Tools", "ToolNumKeys");
        bool hasNotepad = false;
        CompareInfo Compare = CultureInfo.InvariantCulture.CompareInfo;
        for (int i = 0; i < toolCount; i++)
        {
            if (Compare.IndexOf(userSettingsStore.GetString("External Tools", "ToolCmd" + i), "Notepad", CompareOptions.IgnoreCase) >= 0)
            {
                hasNotepad = true;
                break;
            }
        }
    }

    ```

5. Pokud program Poznámkový blok není nastavený jako externího nástroje, nastavte ho následujícím způsobem:

    ```vb
    private void MenuItemCallback(object sender, EventArgs e)
    {
        SettingsManager settingsManager = new ShellSettingsManager(ServiceProvider);
        WritableSettingsStore userSettingsStore = settingsManager.GetWritableSettingsStore(SettingsScope.UserSettings);

        // Find out whether Notepad is already installed.
        int toolCount = userSettingsStore.GetInt32("External Tools", "ToolNumKeys");
        bool hasNotepad = false;
        CompareInfo Compare = CultureInfo.InvariantCulture.CompareInfo;
        for (int i = 0; i < toolCount; i++)
        {
            if (Compare.IndexOf(userSettingsStore.GetString("External Tools", "ToolCmd" + i), "Notepad", CompareOptions.IgnoreCase) >= 0)
            {
                hasNotepad = true;
                break;
            }
        }

        string message = (hasNotepad) ? "Notepad already installed" : "Installing Notepad";
         if (!hasNotepad)
        {
            userSettingsStore.SetString("External Tools", "ToolTitle" + toolCount, "&Notepad");
            userSettingsStore.SetString("External Tools", "ToolCmd" + toolCount, "C:\\Windows\\notepad.exe");
            userSettingsStore.SetString("External Tools", "ToolArg" + toolCount, "");
            userSettingsStore.SetString("External Tools", "ToolDir" + toolCount, "$(ProjectDir)");
            userSettingsStore.SetString("External Tools", "ToolSourceKey" + toolCount, "");
            userSettingsStore.SetUInt32("External Tools", "ToolOpt" + toolCount, 0x00000011);

            userSettingsStore.SetInt32("External Tools", "ToolNumKeys", toolCount + 1);
        }
    }
    ```

6. Testování kódu. Mějte na paměti, že ho Poznámkový blok přidá jako externího nástroje, takže se musí vrátit registru před jejím spuštěním podruhé.

7. Sestavte kód a spusťte ladění.

8. Na **nástroje** nabídky, klikněte na tlačítko **vyvolat UserSettingsStoreCommand**. Tato možnost přidá Poznámkový blok a **nástroje** nabídky.

9. Teď byste měli vidět Poznámkový blok v nabídce Nástroje / možnosti nabídky a kliknutím na **Poznámkový blok** by měl vyvolat instance poznámkového bloku.