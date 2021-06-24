# Sticky Notes
================

## Introduction
------------
Sticky Notes is simple web application built on Zend Framework 2 and uses
the ZF2 MVC layer and module system. This simple application is an extension to
the skeleton application provided by Zend Technologies.

## Installation
------------

## Using Composer (recommended)
----------------------------
* Clone the repository and manually invoke `composer` using the shipped `composer.phar`:
* cd stickynotes
* php composer.phar install

## Database
--------
* Create Database named `stickynotes` and run the following query to create the table and insert sample data.

    -- -----------------------------------------------------
    -- Table `stickynotes`.`stickynotes`
    -- -----------------------------------------------------
    DROP TABLE IF EXISTS `stickynotes`.`stickynotes` ;
    CREATE TABLE IF NOT EXISTS `stickynotes`.`stickynotes` (
    `id` INT NOT NULL AUTO_INCREMENT ,
    `note` VARCHAR(255) NULL ,
    `created` TIMESTAMP NOT NULL ,
    PRIMARY KEY (`id`) ,
    UNIQUE INDEX `id_UNIQUE` (`id` ASC) )
    ENGINE = MyISAM;
    -- -----------------------------------------------------
    -- Data for table `stickynotes`.`stickynotes`
    -- -----------------------------------------------------
    START TRANSACTION;
    USE `stickynotes`;
    INSERT INTO `stickynotes`.`stickynotes` (`id`, `note`, `created`) VALUES (1, 'This is a sticky note you can type and edit.', NOW());
    INSERT INTO `stickynotes`.`stickynotes` (`id`, `note`, `created`) VALUES (2, 'This is another sticky note ', NOW());
    INSERT INTO `stickynotes`.`stickynotes` (`id`, `note`, `created`) VALUES (3, '太奇妙了', NOW());
    COMMIT;

* open config/autoload/global.php and config/autoload/local.php and configure
* your Database credentials.

    // /config/autoload/local.php
    return array(
        'db' => array(
            'username' => 'root',
            'password' => 'DataBabe_Password',
        ),
    );

## Virtual Host
------------
* Afterwards, set up a virtual host to point to the public/ directory of the project and you should be ready to go!

or  may be you can access http://localhost/stickynotes/public/
