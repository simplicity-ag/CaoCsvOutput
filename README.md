CaoCsvOutput
============

Zend Framework 2 Module for generating CSV output from an array.

Installation
------------

### Main Setup

#### By cloning project

1. Install the [CaoCsvOutput](https://github.com/chrisoconnell/CaoCsvOutput) ZF2 module
   by cloning it into `./vendor/`.
2. Clone this project into your `./vendor/` directory.

#### With composer

1. Add this project in your composer.json:

    ```json
    "require": {
        "chrisoconnell/cao-csv-output": "dev-master"
    }
    ```

2. Now tell composer to download CaoCsvOutput by running the command:

    ```bash
    $ php composer.phar update
    ```

#### Post installation

1. Enabling it in your `application.config.php` file.

    ```php
    <?php
    return array(
        'modules' => array(
            // ...
            'CaoCsvOutput',
        ),
        // ...
    );
    ```

Usage
-----
You can either create an instance of `CaoCsvOutput/Model/Csv` or use the view helper
`csvOutput`. 

### Example of Instance
1. Define the data as an array.
2. Create a new instance of `CaoCsvOutput/Model/Csv` using `$data` as the input.
3. Output the result using the `render` method.

    ```php
    $data = array(
      array('a', 1, 'a + b'),
      array('b', '"', ';'),
    );
    $csv = new CaoCsvOutput/Model/Csv($data);
    $output = $csv->render();
    ```
4. Which will set `$output` to be
  
    ```
    a;1;"a + b"
    b;"""";";"
    ```
