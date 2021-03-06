[resvg](https://github.com/RazrFalcon/resvg) test suite

## Notes

- We doesn't test basic shapes rendering with different styles
  because they will be converted to paths anyway. So we can test only them.
- `stroke` attribute tests doesn't duplicate color parsing tests form the `fill` attribute tests.
  They should be processed in the same way.

## Structure

- `images/` - raster images.
- `site/` - sources for github pages.
- `svg/` - SVG images. Actual tests.
- `tools/` - various testing tools.
- `_config.yml`, `Gemfile`, `Rakefile` - configs required for github pages.
- `check.py` - pre-commit hook.
- `gen-table.py` - asciidoctor tables generator.
- `init_official_test_suite.py` - download and prepare the official SVG test suite.
- `official.csv` - results of manual testing via `tools/vdiff` of the official SVG test suite.
- `order.txt` - custom tests order for pretty-printing.
- `outline.py` - pretty-prints tests.
- `results.csv` - results of manual testing via `tools/vdiff` of the `resvg` test suite.
- `stats.py` - generates `site/images/chart.svg`.

### Tests order

Test names must not be changed. All new test files should increment the latest number.
But if we need to insert some test in the middle of the order - we also have to increment
all the tests after it. Which is unacceptable. To avoid this we are using `order.txt` file, that allows us to print
tests in any order we want.

## License

MIT
