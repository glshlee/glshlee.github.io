---
title: Hello, Concurrent World!
author: glshlee
date: 2021-01-19
categories: [kotlin]
tags: [kotlin, concurrent]
---

## 알아야 할 것
프로세스, 스레드, 코루틴 차이 알아보기

## gradle dependency
``` kotlin
repositories {
    mavenCentral()
    jcenter()
}

dependencies {
    implementation(kotlin("stdlib"))
    implementation("org.jetbrains.kotlinx:kotlinx-coroutines-core:1.4.2")
}
```

## test code
``` kotlin
fun main(args: Array<String>) = runBlocking {
    println("${Thread.activeCount()} threads active at the start")
    val time = measureTimeMillis {
        createCoroutines(3)
    }
    println("${Thread.activeCount()} threads active at end")
    println("Took $time ms")
}

suspend fun createCoroutines(amount: Int) {
    val jobs = ArrayList<Job>()
    for (i in 1..amount) {
        jobs += GlobalScope.launch {
            println("Started $i in ${Thread.currentThread().name}")
            delay(1000)
            println("Finished $i in ${Thread.currentThread().name}")
        }
    }
    jobs.forEach {
        it.join()
    }
}
```

## 정리
동시성은 애플리케이션이 동시에 한 개 이상의 스레드에서 실행될 때 발생합니다. 즉, 동시성이 발생하려면 두 개 이상의 스레드가 생성돼야 합니다.