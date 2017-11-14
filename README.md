# How to rebuild and deploy this photo page

Jekyll and Gulp must be installed. Available Gulp tasks are:

| **build**        |    Run all site-generating tasks: sass, js, graphics, icons, htaccess then jekyll
| **deploy**       |    Deploys the site to GitHub.
| **graphics**     |    Compress site graphics and aggregate icons
| **index**        |    Scan for new and deleted photos and albums, merge with the index
| **index-move**   |    Move index into position
| **jekyll**       |    Run jekyll build
| **js**           |    JS/Photoswipe aggregation/minify, custom JS linting
| **lint**         |    Lint all non-vendor JS
| **photos**       |    Rebuild all image derivatives: original, medium, thumb, mini. WARNING: takes a long time if there are lots of photos.
| **prime-posts**  |    Create stub post files for any albums that don't have them already
| **sass**         |    Compile Sass to CSS
| **update**       |    Add/remove photos and albums: index, photos, prime-posts, and jekyll. WARNING: takes a long time if there are lots of photos..

To deploy after adding photos, run `gulp update`, then `gulp build`, then `gulp deploy`. However, this will rebuild the YAML photo index, removing all `hero` tags. I need a way to assign hero images so that this doesn't happen. In the meantime, the hero tags can be added like `hero: 1` to the appropriate images in `_data/index.yml` after running `gulp update` but before running `gulp build`.

To deploy after making site changes that don't involve adding or removing photos, just run `gulp build` and then `gulp deploy`.