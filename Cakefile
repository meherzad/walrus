fs    = require 'fs'
path  = require 'path'
exec  = require( 'child_process' ).exec

sh = ( command, callback ) ->

  exec command, ( error, stdout, stderr ) ->

    console.log error  if error?
    console.log stdout if stdout?
    console.log stderr if stderr?

    callback( ) if callback?

mv = ( from, to ) -> fs.renameSync from, to

task 'compile', 'Compile the walrus parser', ->

  sh 'jison src/walrus.yy src/walrus.l', ->

    mv './walrus.js', './lib/walrus/parser.js'

task 'test', 'Run the test suite', ->

  sh 'jasmine-node --coffee spec'
