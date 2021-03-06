Config-Win32
============

Config::Win32 - Load and save configuration values on Windows

SYNOPSIS

	use Config::Win32;

	my $cfg = Config::Win32->new("Vendor name", "Application name");

	$cfg->save("key", "value");
	print $cfg->load("key");

DESCRIPTION

	This module is a simple way to save and load configuration options in the
	Windows registry. While other Config modules exist, they mostly rely on
	flat files, which is the norm on Unix systems but not as useful on Windows.

	The registry provides an easy place to store values and this module takes
	advantage of that. It uses the Win32API::Registry low-level API to access
	the values.

ATTRIBUTES

$cfg = Config::Win32->new($vendor_name, $application_name)

	Makes a configuration variable, and creates keys in the registry for the
	vendor and application names under HKEY_LOCAL_USER/Software.

$cfg->app

$cfg->app($application_name)

	Returns the current application name, or switches to a new application
	name, and creates the proper keys in the registry.

$cfg->save($key, $value)

	Saves a key/value pair to the registry under the current vendor and
	application name. All values are assumed to be strings.

$cfg->load($key)

	Returns the current value for $key.

INSTALLATION

To install this module, run the following commands:

	perl Makefile.PL
	make
	make test
	make install

SUPPORT AND DOCUMENTATION

After installing, you can find documentation for this module with the
perldoc command.

    perldoc Config::Win32

You can also look for information at:

    RT, CPAN's request tracker (report bugs here)
        http://rt.cpan.org/NoAuth/Bugs.html?Dist=Config-Win32

    AnnoCPAN, Annotated CPAN documentation
        http://annocpan.org/dist/Config-Win32

    CPAN Ratings
        http://cpanratings.perl.org/d/Config-Win32

    Search CPAN
        http://search.cpan.org/dist/Config-Win32/


COPYRIGHT

	(C) 2014 Patrick Lambert - http://dendory.net

	This library is free software; you can redistribute it and/or
	modify it under the same terms as Perl itself.

