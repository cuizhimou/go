package main

import (
	"flag"
	"fmt"
	"gopkg.in/gomail.v2"
	"strings"
)

func tset(value ...string)  {

}
func main() {
	tolist :=flag.String("tolist","","收件人邮箱、逗号分割")
	flag.Parse()
	fmt.Println(*tolist)
	mail_list :=strings.Split(*tolist,",")
	fmt.Println(mail_list)
	m := gomail.NewMessage()
	m.SetHeader("From","cuizhimou@cogo.club")
	m.SetHeader("To",mail_list...)
	m.SetAddressHeader("Cc", "cuizhimou@cogo.club", "Dan")
	m.SetHeader("Subject", "Hello!")
	m.SetBody("text/html", "Hello <b>Bob</b> and <i>Cora</i>!")
	m.Attach("/Users/cui/Downloads/cogo.jpg")

	d := gomail.NewDialer("smtp.exmail.qq.com", 465, "cuizhimou@cogo.club", "VchqhFBAibiWcUup")

	// Send the email to Bob, Cora and Dan.
	if err := d.DialAndSend(m); err != nil {
		panic(err)
	}
}
