# NAME

QRCode::Base45 - Base45 encoding used in QR codes

# VERSION

Version 0.01

# SYNOPSIS

    use QRCode::Base45;

    my $text_for_qrcode = encode_base45($binary_data);
    my $binary_data = decode_base45($text_from_qrcode);

# DESCRIPTION

This module handles encoding/decoding Base45 data,
as described in
[draft-faltstrom-base45-06](http://www.watersprings.org/pub/id/draft-faltstrom-base45-06.html).
Base45 is used especially in QR codes.

## encode\_base45

Takes arbitrary string as argument, and returs the Base45 representation
of it. Character strings (as opposed to byte strings) are encoded to bytes
as UTF-8 first.

For zero-length strings (undef or '') the empty string is returned.

## decode\_base45

The function takes a textual base45 representation of data,
and tries to decode it. Returned value is a byte string (as this function
cannot know whether the contents should be interpreted as bytes or UTF-8
data (or whatever else). The caller has to decode the characters afterwards,
if needed.

For zero-length input, the empty string is returned.

For invalid inputs, such as strings of length 3n+1 or characters
outside of the Base45 alphabet, this function croak()s.

# AUTHOR

Jan "Yenya" Kasprzak, `<kas at fi.muni.cz>`

# BUGS

Please report any bugs or feature requests to `bug-qrcode-base45 at rt.cpan.org`, or through
the web interface at [https://rt.cpan.org/NoAuth/ReportBug.html?Queue=QRCode-Base45](https://rt.cpan.org/NoAuth/ReportBug.html?Queue=QRCode-Base45).  I will be notified, and then you'll
automatically be notified of progress on your bug as I make changes.

# SUPPORT

You can find documentation for this module with the perldoc command.

    perldoc QRCode::Base45

You can also look for information at:

- RT: CPAN's request tracker (report bugs here)

    [https://rt.cpan.org/NoAuth/Bugs.html?Dist=QRCode-Base45](https://rt.cpan.org/NoAuth/Bugs.html?Dist=QRCode-Base45)

- CPAN Ratings

    [https://cpanratings.perl.org/d/QRCode-Base45](https://cpanratings.perl.org/d/QRCode-Base45)

- Search CPAN

    [https://metacpan.org/release/QRCode-Base45](https://metacpan.org/release/QRCode-Base45)

# ACKNOWLEDGEMENTS

# LICENSE AND COPYRIGHT

This software is copyright (c) 2021 by Jan "Yenya" Kasprzak.

This is free software; you can redistribute it and/or modify it under
the same terms as the Perl 5 programming language system itself.
