# Services

This npm module uses services remotely hosted to render MathML data. However, it is strongly recommended to install these services in your backend. This will allow you, among other things, to customize the backend service and store locally the images generated by MathType.

MathType integration services are available for the following technologies: Java, PHP, .NET and Ruby on Rails. You can download the appropiate services from [here](http://www.wiris.com/en/plugins3/generic/download).

## Install instructions

### Java
To install the Java services follow the steps below:
1. Download the [MathTpe for generic HTML editor - Java](http://www.wiris.com/en/plugins3/generic/download) package.
2. Deploy the **pluginwiris_engine war** file.
3. Add the following line to genericIntegrationProperties before create the new instance of GenericIntegration class:
    ```js
    genericIntegrationProperties.configurationService = '/pluginwiris_engine/app/configurationjs';
    ```
    In the previous example the JavaScript code should be the following:
    ```js
    <script>
        var genericIntegrationProperties = {};
        genericIntegrationProperties.target = document.getElementById("example");
        genericIntegrationProperties.toolbar = document.getElementById("toolbarLocation");
        // Load Java services.
        genericIntegrationProperties.configurationService = '/pluginwiris_engine/app/configurationjs';

        // GenericIntegration instance.
        var genericIntegrationInstance = new WirisPlugin.GenericIntegration(genericIntegrationProperties);
        genericIntegrationInstance.init();
        genericIntegrationInstance.listeners.fire('onTargetReady', {});

        WirisPlugin.currentInstance = this.wiris_generic;
    </script>
    ```

### PHP
To install the PHP services follow the steps below:
1. Download the [MathTpe for generic HTML editor - PHP](http://www.wiris.com/en/plugins3/generic/download) package.
2. Copy the generic_wiris/integration folder into your project.
3. Add the following line to genericIntegrationProperties before create the new instance of GenericIntegration class:
    ```js
    genericIntegrationProperties.configurationService = '/integration/configurationjs.php';
    ```
    In the previous example the JavaScript code should be the following>
    ```js
    <script>
        var genericIntegrationProperties = {};
        genericIntegrationProperties.target = document.getElementById("example");
        genericIntegrationProperties.toolbar = document.getElementById("toolbarLocation");
        // Load PHP services.
        genericIntegrationProperties.configurationService = 'integration/configurationjs.php';

        // GenericIntegration instance.
        var genericIntegrationInstance = new WirisPlugin.GenericIntegration(genericIntegrationProperties);
        genericIntegrationInstance.init();
        genericIntegrationInstance.listeners.fire('onTargetReady', {});

        WirisPlugin.currentInstance = this.wiris_generic;
    </script>
    ```

### .NET
To install the .NET services follow the steps below:
1. Download the [MathTpe for generic HTML editor - ASP.NET](http://www.wiris.com/en/plugins3/generic/download) package.
2. Copy the generic_wiris/integration folder into your project.
3. Add the following line to genericIntegrationProperties before create the new instance of GenericIntegration class:
    ```js
    genericIntegrationProperties.configurationService = 'integration/configurationjs.aspx';
    ```
    In the previous example the JavaScript code should be the following>
    ```js
    <script>
        var genericIntegrationProperties = {};
        genericIntegrationProperties.target = document.getElementById("example");
        genericIntegrationProperties.toolbar = document.getElementById("toolbarLocation");
        // Load Aspx services.
        genericIntegrationProperties.configurationService = 'integration/configurationjs.aspx';

        // GenericIntegration instance.
        var genericIntegrationInstance = new WirisPlugin.GenericIntegration(genericIntegrationProperties);
        genericIntegrationInstance.init();
        genericIntegrationInstance.listeners.fire('onTargetReady', {});

        WirisPlugin.currentInstance = this.wiris_generic;
    </script>
    ```

### Ruby on Rails

To install the Ruby on Rails services follow the steps below:
1. Download the [MathTpe for generic HTML editor - Ruby on Rails](http://www.wiris.com/en/plugins3/generic/download) package.
2. Instal the **wirispluginengine.gem** gem.
    ```
        gem install -l wirispluginengine.gem
    ```
3. Add the following line to genericIntegrationProperties before create the new instance of GenericIntegration class:
    ```js
    genericIntegrationProperties.configurationService = '/wirispluginengine/integration/configurationjs';
    ```
    In the previous example the JavaScript code should be the following:
    ```js
    <script>
        var genericIntegrationProperties = {};
        genericIntegrationProperties.target = document.getElementById("example");
        genericIntegrationProperties.toolbar = document.getElementById("toolbarLocation");
        // Load Ruby on Rails services.
        genericIntegrationProperties.configurationService = '/wirispluginengine/integration/configurationjs';

        // GenericIntegration instance.
        var genericIntegrationInstance = new WirisPlugin.GenericIntegration(genericIntegrationProperties);
        genericIntegrationInstance.init();
        genericIntegrationInstance.listeners.fire('onTargetReady', {});

        WirisPlugin.currentInstance = this.wiris_generic;
    </script>    ```
