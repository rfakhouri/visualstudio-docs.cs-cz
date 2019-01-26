---
title: Spuštění sestavení z integrovaného vývojového prostředí | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- build
ms.assetid: 936317aa-63b7-4eb0-b9db-b260a0306196
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 10f97a5cbc51e2f42af1601e8abd43d1e3529e9d
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54942188"
---
# <a name="start-a-build-from-within-the-ide"></a>Spuštění sestavení z integrovaného vývojového prostředí
Musíte použít vlastní systémy <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildManagerAccessor> ke spuštění sestavení. Tento článek popisuje důvody pro tento požadavek a popisuje proceduru.  

## <a name="parallel-builds-and-threads"></a>Paralelní sestavení a vlákna  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] umožňuje paralelní sestavení, která vyžaduje pro přístup ke společným prostředkům zprostředkování. Systémy projektu mohou spouštět sestavení asynchronně, ale tyto systémy nesmí volat funkce sestavení ze volání je k dispozici zpětných správcem sestavení.  

 Pokud systém projektu změní proměnné prostředí, je nutné nastavit NodeAffinity sestavení na OutOfProc. Tento požadavek znamená, že nemůžete použít objekty hostitel, protože vyžadují uzel uvnitř procesu.  

## <a name="use-ivsbuildmanageraccessor"></a>Use IVSBuildManagerAccessor  
 Následující kód obsahuje metodu, která bude systém projektu můžete použít ke spuštění sestavení:  

```csharp

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