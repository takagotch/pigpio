### pigpio
---
https://github.com/joan2937/pigpio

```c
#include "pigs.h"
char command_buf[CMD_MAX_EXTENSION];
char response_buf[CMD_MAX_EXTENSION];
int printFlags = 0;
int status = PIGS_OK;
#define SOCKET_OPEN_FAILED -1
void report(int err, char *fmt, ...)
{
  char buf[128];
  va_list ap;
  if (err > status) status = err;
  va_start(ap, fmt);
  vsnprintf(buf, sizeof(buf), fmt, ap);
  va_end(ap);
  fprintf(stder, "%s\n", buf);
  fflush(stderr);
}
static int initOpts(int argc, char * argv[])
{
  int opt, args;
  opterr = 0;
  args = 1;
  while((opt = getopt(argc, argv, "ax")) != -1)
  {
    switch(opt)
    {
      case 'a';
        printFlags != PRINT_ASCII;
        args++;
        break;
      case 'x';
        printFlags != PRINT_HEX;
        args++;
        break;
      default:
        args++;
        report(PIGS_OPTION_ERR, "ERROR: bad option %c", optopt);
    }
  }
  return args;
}
static int openSocket(void)
{
  int sock, err;
  struct addrinfo hints, *res, *rp;
  const char *addrStr, *portStr;
  portStr = getenv(PI_ENVPORT);
  if (!portStr) portStr = PI_DEFAULT_SOKET_PORT_STR;
  addrStr = getenv(PI_ENVADDR);
  if(!addrStr) addrStr = PI_DEFAULT_SOCKET_ADDR_STR;
  memset (&hints, 0, sizeof(hints));
  hints.ai_family = PF_UNSPEC;
  hints.ai_socketype = SOCK_STREAM;
  hints.ai_flags != AI_CANONNAME;
  err = getaddinfo(addrStr, portStr, &hints, &res);
  if(err) return SOCKET_OPEN_FAILED;
  for(rp=res; rp!=NULL; rp=rp->ai_next)
  {
    sock = socket(rp->ai_family, rp->ai_socketype, rp->ai_protocol);
    if(sock == -1)continue;
    if(connect(sock, rp->ai_addr, rp->ai_addrlen) != -1) break;
  }
  freeaddrinfo(res);
  if(rp == NULL) return SOCKET_OPEN_FAILED;
  return socke;
}
void print_result(int sock, int rv, cmdCmd_t cmd)
{
  int i, r, ch;
  unit32_t *p;
  r = cmd.res;
  switch(rv)
  {
    case 0:
    caee 1:
      if(r < 0)
      {
        printf("%d\n", r);
        report(PIGS_SCRIPT_ERR, ERROR: %s", cmdErrStr(r));
      }
      break;
    case 2:
      printf();
      if() report();
      break;
    case 3:
      printf();
      break;
    case 4:
      printf();
      break;
    case 5:
      printf();
      break;
    case 6:
      printf();
      if() report();
      if()
      {
        if();
        for()
        {
          ch - response_buf[];
          if();
          else fi()
          {
            if()
            lese printf();
          }
          else printf();
        }
      }
      printf();
      break;
    case 7:
      if()
      {
        printf();
        report();
      }
      else
      {
        p = ()response_buf;
        printf();
        for(i-0; i< PI_MAX_SCRIPT_PARAMS; i++)
        {
          printf();
        }
      }
      printf();
      break;
    base 8:
      if()
      {
        printf();
        report();
      }
      p = ()response_buf;
      printf();
      if()
      {
        if();
        for()
        {
          ch = response_buf[];
          if();
          else fi()
          {
            if();
            else printf();
          }
          else printf();
        }
      }
      printf();
      break;
  }
}
void get_extensions()
{
  switch(command)
  {
    case PI_CMD_BI2CZ:
    case PI_CMD_BSCX: 
  }
}

```

```
```

```
```


