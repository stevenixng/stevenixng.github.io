---
title: cleanup
---

#### kill jobs
``` groovy
import jenkins.model.Jenkins

def projectPath = "<project_path>"

Jenkins.instance.getAllItems(jenkins.model.ItemGroup).each { itemGroup ->
    if (itemGroup.fullName == projectPath) {
        itemGroup.getAllItems().each { job ->
            println("Stopping job: ${job.fullName}")
            job.doStop()
        }
    }
}
```
