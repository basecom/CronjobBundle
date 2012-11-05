basecom/CronjobBundle
=====================

License informations: [LGPL](https://raw.github.com/basecom/CronjobBundle/master/LICENSE)


This bundle was made, to create powerfull and efficient cronjobs wich also can use multithreading (requires the php PCNTL-module).

Example
-------
``` php
<?php

namespace basecom\ExampleBundle\Command;

use basecom\CronjobBundle\Command\CronjobCommand;
use Symfony\Component\Console\Input\InputInterface;
use Symfony\Component\Console\Output\OutputInterface;

class ExampleCommand extends CronjobCommand
{
	protected function configure()
	{
		parent::configure();
		$this->setName('basecom:example');
		 	 ->setDescription('Shows the easy usage of this nice CronjobBundle');
	}

	protected function executeCronjob(InputInterface $input, OutputInterface $output, $loopcount, $preloopResult = null)
	{
		$output->writeln("Hello World!");
	}
}
```
In this basic configuration, the cronjob will run about 50 seconds and between each executeCronjob()-call will be a pause of one second.

If you trigger this command, you will see the "Hello World!"-output about 50 times.


Documentation
-------------
* [Basics](http://github.com/basecom/CronjobBundle/blob/master/docs/01-Basics.md)
* [Multithreading](http://github.com/basecom/CronjobBundle/blob/master/docs/03-Multithreading.md)

