# RFC核心概念
1. Resources
2. Representations
   1. A "representation" is information that is intended to reflect a past, current, or desired state of a given resource, in a format that can be readily communicated via the protocol. A representation consists of a set of representation metadata and a potentially unbounded stream of representation data
3. Connections, Clients, and Servers
4. Messages
5. User Agents
6. Origin Server
   1. The term "origin server" refers to a program that can originate authoritative responses for a given target resource.
7. Intermediaries
8. Caches

# RFC报文格式
RFC对于http报文格式的定义
HTTP-message   = start-line CRLF
                 *( field-line CRLF )
                 CRLF
                 [ message-body ]
	   
start-line     = request-line / status-line	
field-line   = field-name ":" OWS field-value OWS
message-body = *OCTET

	   
request-line   = method SP request-target SP HTTP-version
method         = token
HTTP-version  = HTTP-name "/" DIGIT "." DIGIT
  request-target = origin-form
                 / absolute-form
                 / authority-form
                 / asterisk-form
  origin-form    = absolute-path [ "?" query ]		


status-line = HTTP-version SP status-code SP [ reason-phrase ]  
reason-phrase  = 1*( HTAB / SP / VCHAR / obs-text )

先理解RFC的定义,有助于理解httpclient的类


# apache httpclient
HttpEntity是对RFC中的message-body的封装和加强


# httpclient的样例
https://hc.apache.org/httpcomponents-client-4.5.x/examples.html
