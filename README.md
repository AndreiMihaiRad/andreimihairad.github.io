# About Mvxtheme

Mvxtheme is the Jekyll theme written for MvvmCross, using a responsive design to optimize the display of mobile devices.

## Contributing

Bug reports and pull requests are welcome on GitHub at [MvvmCross](https://github.com/MvvmCross/MvvmCross/).

## Development

To set up your environment to develop this theme, run `bundle install`.

Then run `bundle exec jekyll serve` and open your browser at `http://localhost:4000`. This starts a Jekyll server using this theme.

## License

The theme is available as open source under the terms of the [Microsoft Public License](https://github.com/MvvmCross/MvvmCross/blob/master/LICENSE).

### Extra notes
Pay attention if you choose Fedora distribution. Issues with ruby gem json dependencies which don't come with ruby default. Also some extra dependencies should be installed before executing bundle install
`sudo yum install zlib-devel` 
`sudo dnf install rubygem-json`
`sudo dnf install nodejs`
