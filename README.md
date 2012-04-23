REPL
====

    $ lein javac
    Compiling 1 source file to /home/vagrant/immutant-cptest/classes
    $ lein repl
    REPL started; server listening on localhost port 19136
    user=> (use 'immutant-cptest.core) 
    nil
    user=> (hello)
    "Hello SomeClass!"

Deployment
==========

    $ lein immutant deploy

    13:08:24,276 INFO  [org.immutant.core.as] Initializing Immutant Core Subsystem
    13:08:24,327 INFO  [org.immutant.core.as] Welcome to Immutant AS - http://immutant.org/
    13:08:24,328 INFO  [org.immutant.core.as]   version........... 1.x.incremental.261
    13:08:24,329 INFO  [org.immutant.core.as]   build............. 261
    13:08:24,402 INFO  [org.immutant.core.as]   revision.......... 9677d99f1b8caf207baa2ef0d3be245a15d7c596 +modifications
    13:08:24,413 INFO  [org.immutant.core.as]   built with:
    13:08:24,413 INFO  [org.immutant.core.as]     HornetQ......... 2.2.13.Final (HQ_2_2_13_FINAL_AS7, 122)
    13:08:24,414 INFO  [org.immutant.core.as]     JBossAS......... 7.1.1.Final
    13:08:24,414 INFO  [org.immutant.core.as]     Clojure......... 1.3.0
    13:08:24,414 INFO  [org.immutant.core.as]     Infinispan...... 5.1.2.FINAL
    13:08:24,414 INFO  [org.immutant.core.as]     Quartz.......... 1.8.5
    
    [...]
    
    13:22:47,742 INFO  [org.jboss.as.server.deployment] (MSC service thread 1-2) JBAS015876: Starting deployment of "immutant-cptest.clj"
    13:23:01,837 ERROR [org.jboss.msc.service.fail] (MSC service thread 1-1) MSC00001: Failed to start service jboss.deployment.unit."immutant-cptest.clj".INSTALL: org.jboss.msc.service.StartException in service jboss.deployment.unit."immutant-cptest.clj".INSTALL: Failed to process phase INSTALL of deployment "immutant-cptest.clj"
      at org.jboss.as.server.deployment.DeploymentUnitPhaseService.start(DeploymentUnitPhaseService.java:119) [jboss-as-server-7.1.1.Final.jar:7.1.1.Final]
      at org.jboss.msc.service.ServiceControllerImpl$StartTask.startService(ServiceControllerImpl.java:1811) [jboss-msc-1.0.2.GA.jar:1.0.2.GA]
      at org.jboss.msc.service.ServiceControllerImpl$StartTask.run(ServiceControllerImpl.java:1746) [jboss-msc-1.0.2.GA.jar:1.0.2.GA]
      at java.util.concurrent.ThreadPoolExecutor$Worker.runTask(ThreadPoolExecutor.java:886) [rt.jar:1.6.0_21]
      at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:908) [rt.jar:1.6.0_21]
      at java.lang.Thread.run(Thread.java:619) [rt.jar:1.6.0_21]
    Caused by: java.lang.RuntimeException: No such namespace: SomeClass, compiling:(immutant_cptest/core.clj:5)
      at clojure.lang.Compiler.analyze(Compiler.java:6235)
      at clojure.lang.Compiler.analyze(Compiler.java:6177)
      at clojure.lang.Compiler$InvokeExpr.parse(Compiler.java:3452)
      at clojure.lang.Compiler.analyzeSeq(Compiler.java:6411)
      at clojure.lang.Compiler.analyze(Compiler.java:6216)
      at clojure.lang.Compiler.analyze(Compiler.java:6177)
    
    [...]
