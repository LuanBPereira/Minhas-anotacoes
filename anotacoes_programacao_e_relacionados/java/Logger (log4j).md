___
O Log4j é uma biblioteca de logging que permite registrar diferentes tipos de informações e mensagem em uma aplicação Java. Para gerenciar essas mensagens, o Log4j oferece vários víveis de log, que ajudam a classificar a importância ou severidade das mensagens. Esses níveis são, em ordem de prioridade:

### 1. TRACE

- **Descrição**: O nível TRACE é o mais detalhado e verboso disponível no Log4j. Ele é usado para capturar informações de depuração extremamente detalhadas sobre o funcionamento interno da aplicação.
- **Uso**: É ideal para o diagnóstico de problemas específicos, fornecendo informações sobre o fluxo de execução e variáveis específicas em pontos críticos do código. É especialmente útil durante o desenvolvimento para entender como os dados estão sendo manipulados.
- **Exemplo de Aplicação**: Rastrear a entrada e saída de métodos, monitorar valores intermediários em cálculos complexos ou verificar a execução de loops e condições.
___

### 2. DEBUG

- **Descrição**: O nível DEBUG é um pouco menos detalhado que o TRACE, mas ainda fornece informações significativas para a depuração.
- **Uso**: Utilizado para registrar informações que podem ser úteis durante o desenvolvimento e testes. Ele ajuda os desenvolvedores a entender o comportamento da aplicação e a identificar pontos de falha.
- **Exemplo de Aplicação**: Indicar que um determinado processo foi iniciado, mostrar valores de variáveis antes de uma operação importante, ou relatar a conclusão de uma etapa do processo.
___

### 3. INFO

- **Descrição**: O nível INFO é usado para mensagens informativas que indicam o progresso normal da aplicação.
- **Uso**: Mensagens registradas neste nível geralmente indicam que a aplicação está funcionando conforme esperado. É útil para monitorar eventos importantes que não são erros, mas que ainda precisam ser registrados.
- **Exemplo de Aplicação**: Informar sobre a inicialização da aplicação, relatar o sucesso de operações, ou mostrar quando um determinado módulo foi carregado.
___

### 4. WARN

- **Descrição**: O nível WARN é utilizado para indicar situações que não são erros, mas que podem causar problemas ou merecem atenção.
- **Uso**: Mensagens de aviso podem indicar condições que, embora não sejam críticas, podem se tornar problemáticas se não forem tratadas. Elas alertam os desenvolvedores e administradores sobre possíveis falhas futuras.
- **Exemplo de Aplicação**: Avisar sobre a utilização de funcionalidades obsoletas, problemas de desempenho que não afetam imediatamente a aplicação, ou a entrada de dados que não é ideal, mas ainda assim é aceitável.
___

### 5. ERROR

- **Descrição**: O nível ERROR é utilizado para registrar erros que afetam o fluxo normal da aplicação, mas que não necessariamente causam uma parada completa do sistema.
- **Uso**: Mensagens registradas neste nível indicam que algo não funcionou como deveria, e a operação que falhou pode exigir atenção. Embora a aplicação continue funcionando, há um problema que precisa ser corrigido.
- **Exemplo de Aplicação**: Indicar falhas em operações, como erros de acesso a banco de dados, falhas na leitura de arquivos ou exceções tratadas que afetam um processo específico.
___

### 6. FATAL

- **Descrição**: O nível FATAL é o mais severo e indica erros críticos que geralmente resultam na interrupção do programa.
- **Uso**: Mensagens registradas neste nível indicam situações em que a aplicação não pode continuar a funcionar. Isso pode ocorrer devido a falhas graves de sistema ou erros que comprometem a integridade da aplicação.
- **Exemplo de Aplicação**: Relatar falhas críticas no sistema, como a falta de recursos essenciais ou a incapacidade de inicializar componentes fundamentais.
___

### Resumo dos Níveis de Log

- **TRACE**: Detalhes granulares para depuração extrema.
- **DEBUG**: Informações úteis para o desenvolvimento.
- **INFO**: Relatórios sobre o progresso e status normal.
- **WARN**: Avisos sobre possíveis problemas.
- **ERROR**: Indicações de falhas que afetam operações.
- **FATAL**: Erros críticos que resultam em interrupções.
___

## Exemplos de uso dos loggers

##### Exemplo de configuração do Log4j (`log4j2.xml`)
```XML
<?xml version="1.0" encoding="UTF-8"?>
<Configuration status="WARN">
    <Appenders>
        <Console name="Console" target="SYSTEM_OUT">
            <PatternLayout pattern="%d{yyyy-MM-dd HH:mm:ss} %-5p %c{1} - %m%n"/>
        </Console>
    </Appenders>
    <Loggers>
        <Root level="DEBUG">
            <AppenderRef ref="Console"/>
        </Root>
    </Loggers>
</Configuration>
```
___

##### 1. TRACE
O nível `TRACE` é usado para informações detalhadas que são úteis para deputação.
```java
import org.apache.logging.log4j.LogManager;
import org.apache.logging.log4j.Logger;

public class ExemploTrace {
    private static final Logger logger = LogManager.getLogger(ExemploTrace.class);
    
    public static void main(String[] args) {
        logger.trace("Esta é uma mensagem TRACE");
        // Detalhes adicionais da operação
        int valor = 5;
        logger.trace("O valor atual é: {}", valor);
    }
}
```

___
##### 2. DEBUG
O nível `DEBUG` é usado para registrar informações úteis durante o desenvolvimento.
```java
import org.apache.logging.log4j.LogManager;
import org.apache.logging.log4j.Logger;

public class ExemploDebug {
    private static final Logger logger = LogManager.getLogger(ExemploDebug.class);
    
    public static void main(String[] args) {
        logger.debug("Iniciando o processo de cálculo.");
        int resultado = calcular(10, 20);
        logger.debug("Resultado do cálculo: {}", resultado);
    }
    
    private static int calcular(int a, int b) {
        return a + b;
    }
}
```

##### 3. INFO
O nível `INFO` é usado para mensagens informativas que indicam progresso em uma operação.
```java
import org.apache.logging.log4j.LogManager;
import org.apache.logging.log4j.Logger;

public class ExemploInfo {
    private static final Logger logger = LogManager.getLogger(ExemploInfo.class);
    
    public static void main(String[] args) {
        logger.info("Aplicação iniciada com sucesso.");
        processarDados();
        logger.info("Aplicação finalizada.");
    }
    
    private static void processarDados() {
        logger.info("Processando dados...");
        // Simulação de processamento
    }
}
```

##### 4. WARN
O nível `WARN` é usado para indicar situações que não são erros, mas podem causar problemas.
```java
import org.apache.logging.log4j.LogManager;
import org.apache.logging.log4j.Logger;

public class ExemploWarn {
    private static final Logger logger = LogManager.getLogger(ExemploWarn.class);
    
    public static void main(String[] args) {
        int idade = 15;
        if (idade < 18) {
            logger.warn("O usuário é menor de idade: {}", idade);
        } else {
            logger.info("O usuário é maior de idade.");
        }
    }
}
```

##### 5. ERROR
O nível `ERROR` é usado para registrar erros que podem impedir que uma operação seja concluída, mas não interrompem a aplicação.
```java
import org.apache.logging.log4j.LogManager;
import org.apache.logging.log4j.Logger;

public class ExemploError {
    private static final Logger logger = LogManager.getLogger(ExemploError.class);
    
    public static void main(String[] args) {
        try {
            int resultado = dividir(10, 0);
        } catch (ArithmeticException e) {
            logger.error("Erro ao tentar dividir por zero: {}", e.getMessage());
        }
    }
    
    private static int dividir(int a, int b) {
        return a / b;
    }
}
```

##### 6. FATAL
O nível `FATAL` é usado para erros muito graves que pode levar à interrupção do programa.
```java
import org.apache.logging.log4j.LogManager;
import org.apache.logging.log4j.Logger;

public class ExemploFatal {
    private static final Logger logger = LogManager.getLogger(ExemploFatal.class);
    
    public static void main(String[] args) {
        try {
            iniciarAplicacao();
        } catch (Exception e) {
            logger.fatal("A aplicação encontrou um erro fatal: {}", e.getMessage();
        }
    }
    
    private static void iniciarAplicacao() throws Exception {
        throw new Exception("Erro crítico no início da aplicação.");
    }
}
```
___
