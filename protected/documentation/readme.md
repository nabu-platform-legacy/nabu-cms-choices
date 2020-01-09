create table multiple_choices (
	id varchar2(36) primary key,
	created timestamp not null,
	modified timestamp not null,
	category_id varchar2(36) not null,
	name varchar2(4000) not null,
	description varchar2(4000),
	owner_id varchar2(36),
	foreign key (category_id) references master_data_categories(id),
	foreign key (owner_id) references nodes(id)
);
create table multiple_choice_options (
	id varchar2(36) primary key,
	created timestamp not null,
	modified timestamp not null,
	entry_id varchar2(36) not null,
	priority integer not null,
	description varchar2(4000),
	icon varchar2(4000),
	multiple_choice_id varchar2(36) not null,
	foreign key (entry_id) references master_data_entries(id),
	foreign key (multiple_choice_id) references multiple_choices(id)
);
