# DoctrineOrmServiceProvider

The *DoctrineOrmServiceProvider* provides integration with the [Doctrine ORM][1]
for easy database access

## Install

```sh
composer require doctrine/orm "^2.5"
```

## Parameters

 * **doctrine.orm.em.options**:
   Array of Entity Manager options.

   These options are available:
   * **connection** (Default: default):
     String defining which database connection to use. Used when using
     named databases via **dbs**.
   * **mappings**:
     Array of mapping definitions.

     Each mapping definition should be an array with the following
     options:
     * **type**: Mapping driver type, one of `annotation`, `xml`, `yml`, `simple_xml`, `simple_yml` or `php`.
     * **namespace**: Namespace in which the entities reside.

     Additionally, each mapping definition should contain one of the
     following options:
     * **path**: Path to where the mapping files are located. This should
       be an actual filesystem path. For the php driver it can be an array
       of paths
     * **resources_namespace**: A namespaceish path to where the mapping
       files are located. Example: `Path\To\Foo\Resources\mappings`

     Each mapping definition can have the following optional options:
     * **alias** (Default: null): Set the alias for the entity namespace.

     Each **annotation** mapping may also specify the following options:
     * **use_simple_annotation_reader** (Default: true):
       If `true`, only simple notations like `@Entity` will work.
       If `false`, more advanced notations and aliasing via `use` will
       work. (Example: `use Doctrine\ORM\Mapping AS ORM`, `@ORM\Entity`)
       Note that if set to `false`, the `AnnotationRegistry` will probably
       need to be configured correctly so that it can load your Annotations
       classes.
   * **query_cache** (Default: setting specified by orm.default_cache):
     String or array describing query cache implementation.
   * **metadata_cache** (Default: setting specified by orm.default_cache):
     String or array describing metadata cache implementation.
   * **result_cache** (Default: setting specified by orm.default_cache):
     String or array describing result cache implementation.
   * **hydration_cache** (Default: setting specified by orm.default_cache):
     String or array describing hydration cache implementation.
   * **types**
     An array of custom types in the format of 'typeName' => 'Namespace\To\Type\Class'
 * **doctrine.orm.ems.options**:
   Array of Entity Manager configuration sets indexed by each Entity Manager's
   name. Each value should look like **doctrine.orm.em.options**.
 * **doctrine.orm.ems.default** (Default: first Entity Manager processed):
   String defining the name of the default Entity Manager.
 * **doctrine.orm.proxies_dir**:
   String defining path to where Doctrine generated proxies should be located.
 * **doctrine.orm.proxies_namespace** (Default: DoctrineProxy):
   String defining namespace in which Doctrine generated proxies should reside.
 * **doctrine.orm.auto_generate_proxies**:
   Boolean defining whether or not proxies should be generated automatically.
 * **doctrine.orm.class_metadata_factory_name**: Class name of class metadata factory.
   Class implements `Doctrine\Common\Persistence\Mapping\ClassMetadataFactory`.
 * **doctrine.orm.default_repository_class**: Class name of default repository.
   Class implements `Doctrine\Common\Persistence\ObjectRepository`.
 * **doctrine.orm.repository_factory**: Repository factory, instance `Doctrine\ORM\Repository\RepositoryFactory`.
 * **doctrine.orm.entity_listener_resolver**: Entity listener resolver, instance
   `Doctrine\ORM\Mapping\EntityListenerResolver`.
 * **doctrine.orm.default_cache**:
   String or array describing default cache implementation.
 * **doctrine.orm.add_mapping_driver**:
   Function providing the ability to add a mapping driver to an Entity Manager.

   These params are available:
    * **$mappingDriver**:
      Mapping driver to be added,
      instance `Doctrine\Common\Persistence\Mapping\Driver\MappingDriver`.
    * **$namespace**:
      Namespace to be mapped by `$mappingDriver`, string.
    * **$name**:
      Name of Entity Manager to add mapping to, string, default `null`.
 * **doctrine.orm.strategy**:
   * **naming**: Naming strategy, instance `Doctrine\ORM\Mapping\NamingStrategy`.
   * **quote**: Quote strategy, instance `Doctrine\ORM\Mapping\QuoteStrategy`.
 * **doctrine.orm.custom.functions**:
   * **string**, **numeric**, **datetime**: Custom DQL functions, array of class names indexed by DQL function name.
     Classes are subclasses of `Doctrine\ORM\Query\AST\Functions\FunctionNode`.
   * **hydration_modes**: Hydrator class names, indexed by hydration mode name.
     Classes are subclasses of `Doctrine\ORM\Internal\Hydration\AbstractHydrator`.


## Services

## Registering

### Single connection

```php

```

### Multiple connections

```php

```

## Usage

### Single connection

```php

```

### Multiple connections

```php

```

(c) Beau Simensen <beau@dflydev.com> (https://github.com/dflydev/dflydev-doctrine-orm-service-provider)

[1]: https://www.doctrine-project.org/projects/orm
