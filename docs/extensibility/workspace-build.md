---
title: Pracovní prostor sestavení v sadě Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 02/21/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
ms.assetid: 813f7a5e-f298-4469-9f4c-a5bddf5a6e14
author: vukelich
ms.author: svukel
manager: viveis
ms.workload:
- vssdk
ms.openlocfilehash: f7415c99c68436519f9bab721fe88a48f750fa1c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="workspace-build"></a>Pracovní prostor sestavení

Podpora sestavení [otevřít složku](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md) scénáře vyžaduje extender k poskytování [indexované](workspace-indexing.md) a [kontext souboru](workspace-file-contexts.md) dat pro [prostoru](workspaces.md), jako a taky sestavení akci pro spuštění.

Dole je přehled toho, co bude potřebovat rozšíření.

## <a name="build-file-context"></a>Vytvoření souboru kontextu

- Objekt pro vytváření zprostředkovatelů
  - `ExportFileContextProviderAttribute` atribut s `supportedContextTypeGuids` jako všechny použitelné `string` konstanty z `BuildContextTypes`
  - Implementuje `IWorkspaceProviderFactory<IFileContextProvider>`
  - Soubor zprostředkovatele kontextu
    - Vrátí `FileContext` pro každé sestavení operace a konfigurace podporována
      - `contextType` Z <xref:Microsoft.VisualStudio.Workspace.Build.BuildContextTypes>
      - `context` implementuje <xref:Microsoft.VisualStudio.Workspace.Build.IBuildConfigurationContext> s `Configuration` vlastnost jako je konfigurace sestavení (například `"Debug|x86"`, `"ret"`, nebo `null` Pokud není k dispozici). Můžete taky použít instanci <xref:Microsoft.VisualStudio.Workspace.Build.BuildConfigurationContext>. Hodnota konfigurace **musí** odpovídat konfiguraci z hodnoty data indexované souboru.

## <a name="indexed-build-file-data-value"></a>Hodnota dat souboru indexované sestavení

- Objekt pro vytváření zprostředkovatelů
  - `ExportFileScannerAttribute` atribut s `IReadOnlyCollection<FileDataValue>` jako podporovaného typu.
  - Implementuje `IWorkspaceProviderFactory<IFileScanner>`
- Skener souboru na `ScanContentAsync<T>`
  - Vrací data při `FileScannerTypeConstants.FileDataValuesType` je argument typu
  - Vrací hodnotu data soubor pro každou konfiguraci zkonstruovat s:
    - `type` jako `BuildConfigurationContext.ContextTypeGuid`
    - `context` jako konfiguraci sestavení (například `"Debug|x86"`, `"ret"`, nebo `null` Pokud není k dispozici). Tato hodnota **musí** odpovídat konfiguraci z kontextu souboru.

## <a name="build-file-context-action"></a>Kontext akce souboru sestavení

- Objekt pro vytváření zprostředkovatelů
  - `ExportFileContextActionProvider` atribut s `supportedContextTypeGuids` jako všechny použitelné `string` konstanty z `BuildContextTypes`
  - Implementuje `IWorkspaceProviderFactory<IFileContextActionProvider>`
- Akce zprostředkovatele na `IFileContextActionProvider.GetActionsAsync`
  - Vrátí `IFileContextAction` odpovídající danou `FileContext.ContextType` hodnota
- Soubor kontext akce
  - Implementuje `IFileContextAction` a <xref:Microsoft.VisualStudio.Workspace.Extensions.VS.IVsCommandItem>
  - `CommandGroup` Vrátí vlastnosti `16537f6e-cb14-44da-b087-d1387ce3bf57`
  - `CommandId` je `0x1000` pro sestavení, `0x1010` pro opětovné sestavení, nebo `0x1020` pro vyčištění

>[!NOTE]
>Vzhledem k tomu `FileDataValue` musí být indexován, bude určitou dobu mezi otevření pracovního prostoru a bodem, kde je soubor hledat sestavení úplné funkce. Zpoždění se zobrazí na první otevřete složku, protože neexistuje žádný index uložené v mezipaměti.

## <a name="reporting-messages-from-a-build"></a>Generování sestav zprávy ze sestavení

Sestavení mohou prezentovat informace, upozornění a chybové zprávy pro uživatele jedním ze dvou způsobů. Jednoduchý způsob je použít <xref:Microsoft.VisualStudio.Workspace.Build.IBuildMessageService> a poskytují <xref:Microsoft.VisualStudio.Workspace.Build.BuildMessage>, například takto:

```csharp
using Microsoft.VisualStudio.Workspace;
using Microsoft.VisualStudio.Workspace.Build;

private static void OutputBuildMessage(IWorkspace workspace)
{
    IBuildMessageService buildMessageService = workspace.GetBuildMessageService();

    if (buildMessageService != null)
    {
      // Example error build message. See the documentation for BuildMessage for more information.
      var message = new BuildMessage()
      {
          Type = BuildMessage.TaskType.Error,
          Code = "MY1001",
          TaskText = "This is a sample error",
          ProjectFile = "buildfile.bld",
          File = "sourcefile.src"
          LogMessage = $"This is sample text that will only go to the Build output window pane.\n"

          // And any other properties to set
      };

      buildMessageService.ReportBuildMessages(new BuildMessage[] { message });
    }
}
```

`BuildMessage.Type` a `BuildMessage.LogMessage` řídí chování kde informace jsou poskytovány uživateli. Všechny `BuildMessage.TaskType` hodnoty jiné než `None` vytvoří **seznam chyb** položku s danou podrobnosti. `LogMessage` bude vždy výstup v **sestavení** podokně **výstup** okno nástroje.

Alternativně můžete rozšíření přímo komunikovat s **seznam chyb** nebo **sestavení** podokně. Chyby v verze starší než verze 15.7 sady Visual Studio 2017 existuje kde `pszProjectUniqueName` argument <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindowPane2.OutputTaskItemStringEx2*> je ignorována.

>[!WARNING]
>Volající `IFileContextAction.ExecuteAsync` můžete zadat libovolný základní implementace pro `IProgress<IFileContextActionProgressUpdate>` argument. Nikdy vyvolání `IProgress<IFileContextActionProgressUpdate>.Report(IFileContextActionProgressUpdate)` přímo. Aktuálně neexistují žádné obecné pokyny k používání tento argument, ale tato pravidla se mohou změnit.

## <a name="build-related-apis"></a>Rozhraní API související s sestavení

- <xref:Microsoft.VisualStudio.Workspace.Build.IBuildConfigurationContext> poskytuje podrobnosti o konfiguraci sestavení.
- <xref:Microsoft.VisualStudio.Workspace.Build.IBuildMessageService> Zobrazuje <xref:Microsoft.VisualStudio.Workspace.Build.BuildMessage>s uživatelům.

## <a name="tasksvsjson-and-launchvsjson"></a>Tasks.vs.JSON a launch.vs.json

Informace o vytváření souboru tasks.vs.json nebo launch.vs.json, najdete v části [přizpůsobení sestavení a ladění úloh](../ide/customize-build-and-debug-tasks-in-visual-studio.md).

## <a name="next-steps"></a>Další kroky

* [Jazyk serveru protokol](language-server-protocol.md) – zjistěte, jak integrovat jazyk servery do sady Visual Studio.