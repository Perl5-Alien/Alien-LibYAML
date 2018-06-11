# Alien::LibYAML [![Build Status](https://secure.travis-ci.org/Perl5-Alien/Alien-LibYAML.png)](http://travis-ci.org/Perl5-Alien/Alien-LibYAML)

Build and install libyaml, a C-based YAML parser and emitter

# SYNOPSIS

In your Build.PL:

    use Module::Build;
    use Alien::LibYAML;
    my $builder = Module::Build->new(
      ...
      configure_requires => {
        'Alien::LibYAML' => '0',
        ...
      },
      extra_compiler_flags => Alien::LibYAML->cflags,
      extra_linker_flags   => Alien::LibYAML->libs,
      ...
    );
    
    $build->create_build_script;

In your Makefile.PL:

    use ExtUtils::MakeMaker;
    use Config;
    use Alien::LibYAML;
    
    WriteMakefile(
      ...
      CONFIGURE_REQUIRES => {
        'Alien::LibYAML' => '0',
      },
      CCFLAGS => Alien::LibYAML->cflags . " $Config{ccflags}",
      LIBS    => [ Alien::LibYAML->libs ],
      ...
    );

# DESCRIPTION

This distribution provides an alien wrapper for libyaml. It requires a C
compiler. That's all!

# SEE ALSO

- [YAML::XS](https://metacpan.org/pod/YAML::XS)

    Perl bindings for libyaml (library bundled with distribution).

# COPYRIGHT AND LICENSE

Copyright © 2014 Richard Simões. libyaml written and copyrighted by Kirill
Simonov. Both libyaml and this distribution are released under the terms of the
**MIT License** and may be modified and/or redistributed under the same or any
compatible license.

# AUTHOR

Original author: Richard Simões (RSIMOES)

Current maintainer: Graham Ollis <plicease@cpan.org>

# COPYRIGHT AND LICENSE

This software is Copyright (c) 2013-2018 by Richard Simões.

This is free software, licensed under:

    The MIT (X11) License
