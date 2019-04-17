---
title: Spuštění sestavení z integrovaného vývojového prostředí | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: conceptual
helpviewer_keywords:
- build
ms.assetid: 936317aa-63b7-4eb0-b9db-b260a0306196
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 94685a2b06b14c232d9e1f79a1d7440e1ceb765b
ms.sourcegitcommit: 53aa5a413717a1b62ca56a5983b6a50f7f0663b3
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/17/2019
ms.locfileid: "59663372"
---
# <a name="starting-a-build-from-within-the-ide"></a>Spuštění sestavení z prostředí IDE
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Musíte použít vlastní systémy <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildManagerAccessor> ke spuštění sestavení. Toto téma popisuje důvody a popisuje proceduru.  
  
## <a name="parallel-builds-and-threads"></a>Paralelní sestavení a vlákna  
 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] umožňuje paralelní sestavení, které vyžaduje pro přístup ke společným prostředkům zprostředkování. Systémy projektu mohou spouštět sestavení asynchronně, ale tyto systémy nesmí volat funkce sestavení ze volání je k dispozici zpětných správcem sestavení.  
  
 Pokud systém projektu změní proměnné prostředí, je nutné nastavit NodeAffinity sestavení na OutOfProc. To znamená, že nemůžete použít objekty hostitel, protože vyžadují uzel uvnitř procesu.  
  
## <a name="using-ivsbuildmanageraccessor"></a>Pomocí IVSBuildManagerAccessor  
 Následující kód obsahuje metodu, která bude systém projektu můžete použít ke spuštění sestavení:  
  
```  
  
public bool Build(Project project, bool isDesignTimeBuild)  
{  
    // Get the accessor from the IServiceProvider interface for the   
    // project system  
    IVsBuildManagerAccessor accessor =  
        serviceProvider.GetService(typeof(SVsBuildManagerAccessor)) as     
        IVsBuildManagerAccessor;  
    bool releaseUIThread = false;  
    try  
    {  
        if(accessor != null)  
        {  
            // Claim the UI thread under the following conditions:  
            // 1. The build must use a resource that uses the UI thread  
            // or,  
            // 2. The build requires the in-proc node AND waits on the   
            // UI thread for the build to complete  
            if(NeedsUIThread)  
            {  
                int result = accessor.ClaimUIThreadForBuild();  
                if(result != S_OK)  
                {  
                     // Not allowed to claim the UI thread right now  
                     return false;  
                }  
                releaseUIThread = true;  
             }  
             if(isDesignTimeBuild)  
             {  
// Start the design time build  
                  int result = accessor.BeginDesignTimeBuild();  
                  if(result != S_OK)  
                  {  
                      // Not allowed to begin a design-time build at  
                      // this time. Try again later.  
                      return false;  
                  }  
             }  
         }  
         bool buildSucceeded = false;  
         // perform project-system specific build set up tasks  
         // Create your BuildRequestData  
         // This assumes a IHostServices variable (hostServices) set   
   // to your host services. If you don't use a project instance   
         // (you build from a file for example) then use another   
         // constructor.  
         BuildRequestData requestData = new   
             BuildRequestData(project.CreateProjectInstance(),   
             "myTarget", hostServices,   
             BuildRequestData.BuildRequestDataFlags.None);  
         // Mark your your submission as Pending  
         BuildSubmission submission =  
              BuildManager.DefaultBuildManager.  
              PendBuildRequest(requestData);  
         // Register the loggers in BuildLoggers  
         if (accessor != null)  
         {  
               foreach (ILogger logger in BuildLoggers)  
               {  
                    accessor.RegisterLogger(submission.SubmissionId,   
                        logger);  
               }  
         }  
         BuildResult buildResult = submission.Execute();  
         return buildResult;  
     }  
     // Clean up resources  
     finally  
     {  
         if(accessor != null)  
         {  
             // Unregister the loggers, if necessary.  
             accessor.UnregisterLoggers(submission.SubmissionId);  
             // Release the UI thread, if used  
             if(releaseUIThread)  
             {  
                  accessor.ReleaseUIThreadForBuild();  
             }  
             // End the design time build, if used  
             if(isDesignTimeBuild)  
             {  
                  accessor.EndDesignTimeBuild();  
             }  
         }  
     }  
}  
  
```
