---
title: Protokolovací nástroje sestavení | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- MSBuild, writing loggers
- MSBuild, logging
- logging [MSBuild]
ms.assetid: fa34810d-185a-4d22-92bd-9852915e5f1d
author: Mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 9d807cee53bebc8ce94e04a325529fc85c35db3d
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="build-loggers"></a>Protokolovací nástroje sestavení
Protokolovací nástroje poskytují způsob, jak můžete přizpůsobit výstup buildu a zobrazení zprávy, chyby nebo výstrahy v reakci na konkrétní sestavení události. Každý protokolovacího nástroje je implementovaný jako třídy rozhraní .NET, která implementuje <xref:Microsoft.Build.Framework.ILogger> rozhraní, která je definována v sestavení Microsoft.Build.Framework.dll.  
  
 Existují dva přístupy, které můžete použít při implementaci protokoly:  
  
-   Implementace <xref:Microsoft.Build.Framework.ILogger> rozhraní přímo.  
  
-   Vaše třída odvozena od třídy pomocné rutiny, <xref:Microsoft.Build.Utilities.Logger>, která je definována v sestavení Microsoft.Build.Utilities.dll. <xref:Microsoft.Build.Utilities.Logger> implementuje <xref:Microsoft.Build.Framework.ILogger> a poskytuje výchozí implementaci některých <xref:Microsoft.Build.Framework.ILogger> členy.  
  
 Toto téma vysvětluje, jak napsat jednoduchý protokolovacího nástroje, která je odvozena z <xref:Microsoft.Build.Utilities.Logger>, a zobrazí zprávy v konzole v reakci na určité události sestavení.  
  
## <a name="registering-for-events"></a>Registrace pro události  
 Účelem protokolovacího nástroje je shromáždit informace o průběhu sestavení udávaný modul sestavení a potom nahlásit tyto informace užitečným způsobem. Všechny protokolovačů musí přepsat <xref:Microsoft.Build.Utilities.Logger.Initialize%2A> metoda, která je, kde protokolovač registruje pro události. V tomto příkladu protokolovač registruje pro <xref:Microsoft.Build.Framework.IEventSource.TargetStarted>, <xref:Microsoft.Build.Framework.IEventSource.ProjectStarted>, a <xref:Microsoft.Build.Framework.IEventSource.ProjectFinished> události.  
  
 [!code-csharp[msbuild_SimpleConsoleLogger#2](../msbuild/codesnippet/CSharp/build-loggers_1.cs)]  
  
## <a name="responding-to-events"></a>Reagování na události  
 Teď, když pro konkrétní události je registrován protokolovacího nástroje, musí se zpracování událostí, když k nim dojde. Pro <xref:Microsoft.Build.Framework.IEventSource.ProjectStarted>, a <xref:Microsoft.Build.Framework.IEventSource.ProjectFinished> události, protokolovacího nástroje je zapíše jednoduše, krátké věty a název souboru projektu zahrnutých v události. Všechny zprávy z protokolovacího nástroje se zapisují do okna konzoly.  
  
 [!code-csharp[msbuild_SimpleConsoleLogger#3](../msbuild/codesnippet/CSharp/build-loggers_2.cs)]  
  
## <a name="responding-to-logger-verbosity-values"></a>Neodpovídá na požadavky hodnoty podrobností protokolovacího nástroje  
 V některých případech můžete chtít pouze protokolování informací z událost, pokud MSBuild.exe **/verbosity** přepínač obsahuje určitou hodnotu. V tomto příkladu <xref:Microsoft.Build.Framework.IEventSource.TargetStarted> obslužné rutiny události pouze zaznamená zprávu, pokud <xref:Microsoft.Build.Utilities.Logger.Verbosity%2A> vlastnosti, která se nastavuje pomocí **/verbosity** přepnout, se rovná <xref:Microsoft.Build.Framework.LoggerVerbosity> `Detailed`.  
  
 [!code-csharp[msbuild_SimpleConsoleLogger#4](../msbuild/codesnippet/CSharp/build-loggers_3.cs)]  
  
## <a name="specifying-a-logger"></a>Určení protokolovacího nástroje.  
 Jakmile protokolovacího nástroje zkompilován do sestavení, budete muset zadat [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] k použití tohoto protokolovacího nástroje během sestavení. To se provádí pomocí **/logger** přepínač s MSBuild.exe. Další informace o přepínačích, které jsou k dispozici pro MSBuild.exe najdete v tématu [Reference k příkazovému řádku](../msbuild/msbuild-command-line-reference.md).  
  
 Následující příkaz vytvoří projekt `MyProject.csproj` a používá třídu protokoly implementované v `SimpleLogger.dll`. **/Nologo** přepínač skryje banner a zpráva o autorských právech a **/noconsolelogger** přepínač zakáže výchozí [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] konzoly protokolovacího nástroje.  
  
```  
MSBuild /nologo /noconsolelogger /logger:SimpleLogger.dll  
```  
  
 Následující příkaz vytvoří projekt se stejným protokolovacího nástroje, ale s `Verbosity` úroveň `Detailed`.  
  
```  
MSBuild /nologo /noconsolelogger /logger:SimpleLogger.dll /verbosity:Detailed  
```  
  
## <a name="example"></a>Příklad  
  
### <a name="description"></a>Popis  
 Následující příklad obsahuje kompletní kód pro protokolovacího nástroje.  
  
### <a name="code"></a>Kód  
 [!code-csharp[msbuild_SimpleConsoleLogger#1](../msbuild/codesnippet/CSharp/build-loggers_4.cs)]  
  
### <a name="comments"></a>Komentáře  
  
## <a name="example"></a>Příklad  
  
### <a name="description"></a>Popis  
 Následující příklad ukazuje, jak implementovat protokolovacího nástroje, který zapíše protokol do souboru místo zobrazení v okně konzoly.  
  
### <a name="code"></a>Kód  
 [!code-csharp[msbuild_BasicLogger#1](../msbuild/codesnippet/CSharp/build-loggers_5.cs)]  
  
### <a name="comments"></a>Komentáře  
  
## <a name="see-also"></a>Viz také  
 [Získávání protokolů o sestavení](../msbuild/obtaining-build-logs-with-msbuild.md)   
 [Koncepty nástroje MSBuild](../msbuild/msbuild-concepts.md)