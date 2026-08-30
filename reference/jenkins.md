# Jenkins Client

Simple client for managing jobs and builds on a Jenkins server. Set a
default access token via the `JENKINS_PAT` environment variable.

## Usage

``` r
jenkins(server = "http://jenkins.ropensci.org", username = "jeroen",
  token = jenkins_pat(), verbose = FALSE)
```

## Arguments

- server:

  base url of the jenkins server

- username:

  name of the jenkins user to login

- token:

  authentication token (or password) for your jenkins server.

- verbose:

  print http output for debugging

## Methods


    ## jk <- jenkins('https://ci.yourserver.com')
    <jenkins>
     $build_info(job_name, build_id = "lastBuild")
     $build_log(job_name, build_id = "lastBuild")
     $build_stop(job_name, build_id = "lastBuild")
     $node_info(node_name = "master")
     $node_list()
     $project_build(job_name, params = list(KEEP_CACHE = "true"))
     $project_build_all(delay = 0.5, shuffle = FALSE, keep_cache = TRUE, update_universe = FALSE)
     $project_config(job_name)
     $project_create(job_name, xml_string)
     $project_delete(job_name)
     $project_disable(job_name)
     $project_enable(job_name)
     $project_list()
     $project_update(job_name, xml_string)
     $queue_cancel(queue_id)
     $queue_cancel_all()
     $queue_info(queue_id)
     $queue_list()
     $server_info()
     $user_info(user_name = username)
     $user_list()
     $view_create(view_name, xml_string)
     $view_delete(view_name)
     $view_info(view_name)
     $view_list()
     $view_update(view_name, xml_string)

## References

<https://wiki.jenkins.io/display/JENKINS/Terminology>

## Examples

``` r
if (FALSE) # This requires a jenkins server
jk <- jenkins(server = 'http://jenkins.ropensci.org', username = 'jeroen')

# Do stuff
jk$server_info()
#> Error: object 'jk' not found
jk$project_build('magick')
#> Error: object 'jk' not found

# It's now in the queue
jk$queue_list()
#> Error: object 'jk' not found

# Check build status
jk$build_info('magick')
#> Error: object 'jk' not found

# Get latest build log
jk$build_log('magick', build_id = 'lastCompletedBuild')
#> Error: object 'jk' not found
 # \dontrun{}
```
