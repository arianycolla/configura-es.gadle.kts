Gerenciamento de plugins {
    val flutterSdkPath =  executar {
        val propriedades = java.util. Propriedades ()
        arquivo( " local.properties " ).inputStream().use { propriedades.load(it) }
        val flutterSdkPath = propriedades.getProperty( " flutter.sdk " )
        require(flutterSdkPath !=  null ) { " flutter.sdk não definido em local.properties " }
        CaminhoSdk fazer Tremulação
    }

    includeBuild( " $flutterSdkPath /pacotes/flutter_tools/gradle " )

    repositórios {
        pesquise no Google()
        mavenCentral()
        gradlePluginPortal()
    }
}

plugins {
    id( " dev.flutter.flutter-plugin-loader " ) versão " 1.0.0 "
    id( " com.android.application " ) versão " 8.7.0 " aplicar falso
    id( " org.jetbrains.kotlin.android " ) versão " 1.8.22 " aplicar falso
}

incluir( " :aplicação " )
