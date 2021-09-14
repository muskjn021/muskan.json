# muskan.json
package com.restassured.api;
import org.json.simple.JSONObject;
import org.testng.annotations.Test;

import io.restassured.http.ContentType;

import static io.restassured.RestAssured.*;

public class test_g {
	@Test
	public void Get_test() {

		baseURI="http://localhost:5000/";
		//GET-1
		given().
		get("/users").then().
		statusCode(200).
		log().all();

		//GET-2
		given().
		param("name", "abc").
		get("/subjects").then().
		statusCode(200).
		log().all();
	}
	@Test
	public void POST_test() {
		baseURI="http://localhost:3000/";
		//POST-1
		JSONObject request = new JSONObject();
    request.put("id", "1");
		request.put("name", "Leanne Graham");
		request.put("username", "Bret");
		request.put("email_address", "Sincere@april.biz");
    request.put("street": "Kulas Light");
    request.put("suite": "Apt. 556");
    request.put("city": "Gwenborough");,
    request.put("zipcode": "92998-3874");

		given().
		contentType(ContentType.JSON).accept(ContentType.JSON).
		header("Content-Type", "application/json").
		body(request.toJSONString()).
		when().
		post("/users").
		then().statusCode(201).
		log().all();
	}
	@Test	
	public void PATCH_test() {
		baseURI="http://localhost:5000/";
		//POST-1
		request.put("id", "2");
		request.put("name", "Ervin Howell");
		request.put("username", "Antonette");
		request.put("email_address", "Shanna@melissa.tv");
    request.put("street": "Victor Plains");
    request.put("suite": "Suite 879");
    request.put("city": "Wisokyburgh");,
    request.put("zipcode": "90566-7771");


		given().
		contentType(ContentType.JSON).accept(ContentType.JSON).
		header("Content-Type", "application/json").
		body(request.toJSONString()).
		when().patch("/users/3").
		then().statusCode(200).
		log().all();
	}
	@Test	
	public void PUT_test1() {
		baseURI="http://localhost:5000/";

		//POST-1
		JSONObject request = new JSONObject();
		request.put("id", "3");
		request.put("name", "Clementine Bauchl");
		request.put("username", "Samantha");
		request.put("email_address", "Nathan@yesenia.net");
    request.put("street": "Douglas Extension");
    request.put("suite": "Suite 847");
    request.put("city": "McKenziehaven");,
    request.put("zipcode": "59590-4157");


		given().
		contentType(ContentType.JSON).accept(ContentType.JSON).
		header("Content-Type", "application/json").
		body(request.toJSONString()).
		when().
		put("/users/6").
		then().statusCode(200).
		log().all();
	}
	@Test	
	public void DELETE_test1() {
		baseURI="http://localhost:5000/";
		JSONObject request = new JSONObject();
		given().
		contentType(ContentType.JSON).accept(ContentType.JSON).
		header("Content-Type", "application/json").
		body(request.toJSONString()).
		when().delete("/users/4").
		then().statusCode(200).
		log().all();
	}
  


}
