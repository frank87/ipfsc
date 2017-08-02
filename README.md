ipfsc
=====

Client for IPFS server. It's https://github.com/hendry19901990/erlang-ipfs-api put in a rebar3-OTP-lib.

Build
-----

    $ rebar3 compile


Using in your rebar project
---------------------------
Add this repo to config.rebar



Quickstart
----------
%% Add Enpoint /api/v0/add
Method: ipfs:add("ip-address", "port", "fullpathFile", "nameFile.extension").
> ipfs:add("127.0.0.1", "5001", "test.txt", "test.txt").
{[{<<"Name">>,<<"test.txt">>},
  {<<"Hash">>,
   <<"QmYAVSgbjdw1hb96aFev6inrnqYntJLboeg8mumBvuamMe">>}]}

%% Cat Enpoint /api/v0/cat
Method: ipfs:add("ip-address", "port", "hash").
>  ipfs:cat("127.0.0.1", "5001", "QmYAVSgbjdw1hb96aFev6inrnqYntJLboeg8mumBvuamMe").
"Hello World"

%% Cat Enpoint /api/v0/ls
Method: ipfs:ls("ip-address", "port", "hash").
>  ipfs:ls("127.0.0.1", "5001", "QmaaqrHyAQm7gALkRW8DcfGX3u8q9rWKnxEMmf7m9z515w").
{[{<<"Objects">>,
   [{[{<<"Hash">>,
       <<"QmaaqrHyAQm7gALkRW8DcfGX3u8q9rWKnxEMmf7m9z515w">>},
      {<<"Links">>,
       [{[{<<"Name">>,<<"index.html">>},
          {<<"Hash">>,
           <<"QmYftndCvcEiuSZRX7njywX2AGSeHY2ASa7VryCq1mKwEw">>},
          {<<"Size">>,1700},
          {<<"Type">>,2}]},
        {[{<<"Name">>,<<"static">>},
          {<<"Hash">>,
           <<"QmdtWFiasJeh2ymW3TD2cLHYxn1ryTuWoNpwieFyJriGTS">>},
          {<<"Size">>,2428803},
          {<<"Type">>,1}]}]}]}]}]}
          
%% Size Enpoint /api/v0/size
Method: ipfs:ls("ip-address", "port", "hash").
>  ipfs:size("127.0.0.1", "5001", "QmaaqrHyAQm7gALkRW8DcfGX3u8q9rWKnxEMmf7m9z515w").   
{[{<<"Hash">>,
   <<"QmaaqrHyAQm7gALkRW8DcfGX3u8q9rWKnxEMmf7m9z515w">>},
  {<<"NumLinks">>,2},
  {<<"BlockSize">>,108},
  {<<"LinksSize">>,106},
  {<<"DataSize">>,2},
  {<<"CumulativeSize">>,2430611}]}
